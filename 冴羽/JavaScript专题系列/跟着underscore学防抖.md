    # JavaScript专题之跟着underscore学防抖

    防抖的原理就是：你尽管触发事件，但是我一定在事件触发 n 秒后才执行，
    如果你在一个事件触发的 n 秒内又触发了这个事件，那我就以新的事件的时间为准，
    n 秒后才执行，总之，就是要等你触发完事件 n 秒内不再触发事件，我才执行，真是任性呐!
    
    function debounce(func, wait, immediate) {

    var timeout, result;

    var debounced = function () {
        var context = this;
        var args = arguments;

        if (timeout) clearTimeout(timeout);
        if (immediate) {

            var callNow = !timeout;
            timeout = setTimeout(function(){
                timeout = null;
            }, wait)
            if (callNow) result = func.apply(context, args)
        }
        else {
            timeout = setTimeout(function(){
                func.apply(context, args)
            }, wait);
        }
        return result;
    };

    debounced.cancel = function() {
        clearTimeout(timeout);
        timeout = null;
    };

    return debounced;
}

//完善
//1:this
//2:event 对象
//3:我不希望非要等到事件停止触发后才执行，
//我希望立刻执行函数，然后等到停止触发 n 秒后，才可以重新触发执行。
//4:返回值
//5:可取消
