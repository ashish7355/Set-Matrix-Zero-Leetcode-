# Set-Matrix-Zero-Leetcode-
Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.  You must do it in place.
class Solution {
    public void setZeroes(int[][] matrix) {
        boolean fRow = false, fCol = false;
        for(int i=0;i<matrix.length;i++){
            for(int j=0;j<matrix[0].length;j++) {
                if(matrix[i][j] == 0){
                    if(i == 0) fRow = true;
                    if(j == 0) fCol = true;
                    matrix[0][j] = 0;
                    matrix[i][0] = 0;
                }
            }
        }
        for(int i=1;i<matrix.length;i++){
            for(int j=1;j<matrix[0].length;j++){
                if(matrix[i][0] == 0 || matrix[0][j] == 0){
                    matrix[i][j] = 0;
                }
            }
        }
        if(fRow){
            for(int j=0;j<matrix[0].length;j++){
                matrix[0][j] = 0;
            }
        }
        if(fCol){
            for(int i=0;i<matrix.length;i++){
                matrix[i][0] = 0;
            }
        }
    }
}
