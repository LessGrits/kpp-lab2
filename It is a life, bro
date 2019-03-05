const height = 20;
const width = 80;

let arrBoard = [];

randomBody = function () {
    let rundNum = Math.random();
    return rundNum > 0.50;
};


function createBoard(arr, random = false) {
    for (let i = 0; i <= height; i++) {
        arr[i] = [];
        for (let j = 0; j <= width; j++) {
            if (i === 0 || j === 0 || i === height || j === width) {
                arr[i][j] = 0
            } else {
                if (random && randomBody()) {
                    arr[i][j] = 1;
                } else {
                    arr[i][j] = 0;
                }
            }

        }
    }
}

function drawBoard(arr) {
    for (let i = 0; i <= height; i++) {
        for (let j = 0; j <= width; j++) {
            if (arr[i][j]) {
                process.stdout.write("@");
            } else {
                process.stdout.write(" ");
            }
        }
        process.stdout.write('\n');
    }
}

function changeLife(arr) {
    arrBoard = [];
    createBoard(arrBoard);
    for (let i = 1; i < height; i++) {
        for (let j = 1; j < width; j++) {
            // if ((calcNeighdors(arr, i, j) === 3)||(arr[i][j] && calcNeighdors(arr,i,j)===2) ) {   //|| (arr[i][j] && (calcNeighdors(arr, i, j) > 1 && calcNeighdors(arr, i, j) < 3))
            //     arr[i][j] = 1;
            // } else {
            //     arr[i][j] = 0;
            // }
            if (!arr[i][j]) {
                if (calcNeighdors(arr, i, j) === 3) {
                    arrBoard[i][j] = 1;
                }
            } else {
                if (calcNeighdors(arr, i, j) === 3 || calcNeighdors(arr, i, j) === 2) {
                    arrBoard[i][j] = 1;
                } else {
                    arrBoard[i][j] = 0;
                }
            }

            // else if ()
            // else {
            //     arr[i][j] = 0;
            // }

        }
    }
}

function calcNeighdors(arr, i, j) {
    /*if (i < 1 || j < 1 || i > height - 1 || j > weidth - 1) {
        return 0
    }*/
    return (arr[i - 1][j - 1] + arr[i - 1][j] + arr[i - 1][j + 1] +
        arr[i][j - 1] + arr[i][j + 1] +
        arr[i + 1][j - 1] + arr[i + 1][j] + arr[i + 1][j + 1]);
}


createBoard(arrBoard, true);
setInterval(function () {
    process.stdout.write('\033c');
    drawBoard(arrBoard);
    changeLife(arrBoard);
}, 200);

