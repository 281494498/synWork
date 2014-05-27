

var start = new Date().getTime();

//var array = ["stuart", "munich", "stuttgartfeuerbach", "stuttgart"];

var fragment = {};
var checked =[];
var THRESHOLD = 5;

array.forEach(function(objectString, index){
    var objectLength = objectString.length;
    for (var i = 0; i < objectLength ; i++) {  //keep cursor from the start of the string
        for (var j = objectLength; j >= (i + THRESHOLD); j--) {  //keep cursor from the end of the string
            var substring = objectString.substring(i, j);

            if(checked.indexOf(substring)=== -1){

                //loop for the rest guys in the array
                array.slice(index + 1).forEach(function (otherString, otherIndex) {
                    var startIndex = 0;
                    var foundPosition = otherString.indexOf(substring, startIndex);
                    while(foundPosition !== -1){
                        //add to our record element
//                    console.log('current string is ' + substring  +' out of ' + otherString);
                        if(fragment.hasOwnProperty(substring)){
                            fragment[substring].push(otherIndex + index + 1);
                        }
                        else{
                            fragment[substring] = [index, index+1+otherIndex];
                        }
                        //replace the fragment in looping string

//                    array[otherIndex] = otherString.slice(foundPosition, foundPosition + substring.length);

                        startIndex = foundPosition + substring.length;
                        foundPosition = otherString.indexOf(substring, startIndex);
                    }
                });
                checked.push(substring);
            }

        }
    }
});

var end = new Date().getTime();
var elapse = end - start;
console.log("used time is"+elapse);
//count the number of the repeated fragments
console.warn('fragments number is:'+Object.keys(fragment).length);
console.log('array of all the checked items are:');
console.dir(checked);
console.log('final fragment statistics:');
console.dir(fragment);
