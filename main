#include<bits/stdc++.h>
#include <iostream>
using namespace std;

void print2dArray(int board[8][8]){
    static int count = 1;
    printf("%d-\n", count++);
    for (int i = 0; i < 8; i++)
    {
        for (int j = 0; j < 8; j++)
            printf(" %d ", board[i][j]);
        printf("\n");
    }
    printf("\n");
}

bool checkValid(int array[8][8], int row, int col){
  int i;
  int j;

  for (i = 0; i < col; i++) 
    if (array[row][i]) 
    return false;

  for (i = row, j = col; i >= 0 && j >= 0; i--, j--) 
    if (array[i][j]) 
    return false;

  for(i = row, j = col; j >= 0 && i < 8; i++, j--){
    if (array[i][j])
    return false;
  }
return true;
}

bool solve(int array[8][8], int col){
  if(col == 8){
    print2dArray(array);
    return true;
  }

  bool temp = false;
  for(int i = 0; i < 8; i++){

    if(checkValid(array, i, col)){
      array[i][col] = 1;
      temp = solve(array, col + 1) || temp;
      array[i][col] = 0;
    }
  }

  return temp;
}

void createBoard(){
    int array[8][8] = {0};
    memset(array, 0, sizeof(array));
 
    if (solve(array, 0) == false)
    {
        cout << "Solution does not exist";
        return ;
    }
 
    return ;
}

int main() {
  createBoard();
  return 0;  

}
