
int numberOfTriangles2(std::vector<int> sticks) {
    int len = sticks.size(), cnt = 0;
    sort(sticks.begin(), sticks.end());
    for(int i = 0; i < len; i++)
    {
        int z = len-1;
        int j = i+1;
        while(z > j)
        {
            if(sticks[i]+sticks[j]>sticks[z])
            {
                cnt+=(len-j-1);
                j++;
            }
            else{
                z--;
            }
        }
    }
    return cnt;
}

You have N sticks. Given an array of their lengths, find the number of triangles that can be constructed using any three of these sticks. Note that the sum of the lengths of any two sides of a triangle must be greater than the third side.

Equal triangles that are constructed from different sticks are considered different.

Example

For sticks = [3, 5, 7, 9], the output should be
numberOfTriangles2(sticks) = 3.

These 3 triangles are (described by their sides): (3, 5, 7), (3, 7, 9), (5, 7, 9).
The triangle (3, 5, 9) is not valid, as 3 + 5 = 8 < 9.

For sticks = [4, 4, 4, 4], the output should be
numberOfTriangles2(sticks) = 4.

These 4 triangles are (4, 4, 4) made of different sticks.

For sticks = [1, 2, 3], the output should be
numberOfTriangles2(sticks) = 0.

There is only one triangle (1, 2, 3), but it is incorrect: 1 + 2 = 3.

Input/Output

[time limit] 500ms (cpp)
[input] array.integer sticks

A sorted array of at least three positive integers.

Constraints:
3 ≤ sticks.length ≤ 10,
1 ≤ sticks[i] ≤ 20.

[output] integer
