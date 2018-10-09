# collection
A simple PHP collection class to be used instead of ArrayObject

Instead of using [ArrayObject](http://php.net/manual/de/class.arrayobject.php) you can use simple collection. 
It implements [ArrayAccess](http://php.net/manual/en/class.arrayaccess.php) and [IteratorAggregate](http://php.net/manual/en/class.iteratoraggregate.php)
so you can use it as an array:

```php
$myCollection = new Collection;
$myCollection[] = 'value1';
$myCollection[] = 'value2';
$myCollection['data'] = 'value3';
```
and you can iterate it 
```php
foreach ($myCollection as $key => $item) {
  //you logic here
}
```
and you can use it as a base for your cool stuff like type hinting

```php
class MyCoolCollection extends Collection
{
  
    public function add(MyCoolInterface $myCoolThing)
    {
        $this->collectionItems[] = $myCoolThing;
        return $this;
    }

    public function offsetGet($offset): MyCoolInterface
    {
        return parent::offsetGet($offset);
    }
}
```
Installation:

```
composer require damijanc/collection
```
