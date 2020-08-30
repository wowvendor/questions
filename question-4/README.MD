###### **Что выведет данный php код?**

```
    interface MyInterface{
        public function foo(): string;
    }
    
    final class AbstractClass implements MyInterface {
    
        public function foo(): string
        {
            return 'bar';
        }
    
    }
    
    class FooBar extends AbstractClass{
    
        public function __construct()
        {
            if(method_exists($this, 'foo')){
                echo $this->foo();
            } else {
                echo 'bar';
            }
            
        }
    
    }
    
    new FooBar();
```