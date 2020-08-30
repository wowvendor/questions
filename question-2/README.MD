###### **Что выведет данный php код?**

```
    interface Interface{
        public function beforeInit(): void;
        public function afterInit(): void;
    }
    
    abstract class AbstractClass implements Interface
    {
    
        protected $string;
    
        public function __construct()
        {
            $this->beforeInit();
            $this->afterInit();
        }
    
        public function beforeInit(): void
        {
            $this->string = 'I\'m Abstract string!';
        }
    
    }
    
    final class Class extends AbstractClass
    {
    
        public function beforeInit(): void
        {
            $this->string = 'I\'m Class string!';
        }
    
        public function afterInit(): void
        {
            echo $this->string;
        }
    }
    
    new Class();
```