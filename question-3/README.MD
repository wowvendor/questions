###### **Что выведет данный php код?**

```
    abstract class AbstractController{
    
    
        protected static $_instance = null;
    
        protected function __construct()
        {
            $this->onInit();
        }
    
        abstract protected function onInit(): void;
    
        public static function instance()
        {
            if (is_null(static::$_instance)) {
                static::$_instance = new static();
            }
    
            return static::$_instance;
        }
    
        protected function getVariable($variable_name)
        {
            return $this->{$variable_name};
        }
    
    }
    
    class Main extends AbstractController
    {
        protected static $_instance = null;
    
        private $class_a;
    
        private $class_b;
    
        private $class_c;
    
        protected function onInit(): void
        {
            $this->class_c = ClassC::instance();
            $this->class_b = ClassB::instance();
            $this->class_a = ClassA::instance();
        }
    
    }
    
    class ClassA extends AbstractController {
    
        protected function onInit(): void
        {
            echo 'i\'m Class A!';
        }
    }
    
    class ClassB extends AbstractController {
    
        protected function onInit(): void
        {
            echo 'i\'m Class B!';
        }
    }
    
    class ClassC extends AbstractController {
        protected function onInit(): void
        {
            echo 'i\'m Class C!';
        }
    }
    
    $main = Main::instance();
```