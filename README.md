Yii2 Masonry ListView Widget
======================

Yii2 widget to extend the Yii2 ListView for use it as Masonry grid layout (http://masonry.desandro.com/)

Widget demo screenshot:
![masonry-view-demo](https://cloud.githubusercontent.com/assets/5610788/17868085/7fc5279a-68ad-11e6-92ff-963f4781d4a8.png)

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist nerburish/yii2-masonry-view "dev-master"
```

or add

```
"nerburish/yii2-masonry-view": "dev-master"
```

to the require section of your `composer.json` file.


Usage
-----

The usage is similar to default ListView Widget (http://www.yiiframework.com/doc-2.0/yii-widgets-listview.html)

You just need a dataProvider and prepare the item template for your model.

In clientOptions you can pass the Masonry options to modify the plugin behavior (see http://masonry.desandro.com/options.html)

You can also attach a cssFile for styling the grid.

Exemple
-----

We have this model:

```
class MyModel extends \yii\base\Theme
{
	public $id;
	
	public $title;
	
	public $description;
}
```

And this item template named _item.php:

```
<h3><?= $model->title ?></h3>
<p><?= $model->description ?></p>
```

Finally, in our view, we run the widget:

```
<?php echo \nerburish\masonryview\MasonryView::widget([
	'dataProvider' => $dataProvider,
	'itemView' => '_item',
	'clientOptions' => [
	  'gutterWidth' => 15,
	],
	'cssFile' => [
		"@web/css/masonry-demo.css"		
	]
]) ?>
```

Below, the css used for the demo:

```
/* ---- grid ---- */
.grid {
  box-sizing: border-box;
}

/* clearfix */
.grid:after {
  content: '';
  display: block;
  clear: both;
}

/* ---- grid-item ---- */
.grid-item {
  width: 20%;
  padding: 10px;  
  margin: 10px auto;
  float: left;
  background: #e4e4e4;
  border-radius: 5px;
}
```

You may be interested in Isotope Widget because implements Masonry and other layouts and funcionalities at once.
https://github.com/nerburish/yii2-isotope-view

There is also a MatchHeight.js implementation of ListView widget:
https://github.com/nerburish/yii2-match-height-view


 
