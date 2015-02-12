Ionic Contrib: Swipeable Cards
===================

Swipeable card based layout for Ionic and Angular. As seen in apps like [Jelly](http://jelly.co/)

[Demo](http://codepen.io/ionic/pen/nxEdH)

## Usage

Include `ionic.tdcards.js` after the rest of your Ionic and Angular includes. Then use the following AngularJS directives:

```html
<td-cards>
  <td-card ng-repeat="card in cards" on-destroy="cardDestroyed($index)" on-swipe="cardSwiped($index)">
    Card content here
  </td-card>
</td-cards>
```

To add new cards dynamically, just add them to the cards array:

```javascript
$scope.cards = [
  { // card 1 },
  { // card 2 }
];

$scope.cardDestroyed = function(index) {
  $scope.cards.splice(index, 1);
};

$scope.cardSwiped = function(index) {
  var newCard = // new card data
  $scope.cards.push(newCard);
};
```
With added support for directional swipe control

```html
<td-cards>
  <td-card ng-repeat="card in cards" directions="left-up" on-swiped="cardSwiped($index, direction)">
    Will Only Support Left And Up Swipes
  </td-card>
</td-cards>
```
on-swipe returns a direction: "left", "right", "up","down"
```javascript

$scope.cardSwiped = function(index, direction) {
 	switch(direction){
 		case 'left': doSomething();
 		break;
 		case 'up': doSomething();
 		...
 		}

};
```




