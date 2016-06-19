Given a connected undirected weighted graph (possibly with cycles) as its adjacency matrix, calculate its radius.

The radius of a graph is the minimum eccentricity of any vertex, where the eccentricity of a vertex v is the greatest distance between v and any other vertex.

For more information on how distances are calculated, check out this page.

Example

For

matrix = [[-1, -1, 1, 3],
          [-1, -1, -1, 2],
          [1, -1, -1, 7],
          [3, 2, 7, -1]]
the output should be giveMeRadius(matrix) = 4.



In this example eccentricity of the first vertex is 5, the second vertex is 6, the third vertex is 6, and the fourth vertex is 4. So, radius = min({5,6,6,4}) = 4.

Input/Output

[time limit] 500ms (cpp)
[input] array.array.integer matrix

Adjacency matrix of the given graph, which is guaranteed to be symmetric. If matrix[i][j] > 0, the distance between vertices i and j is matrix[i][j]. Otherwise matrix[i][j] = -1, meaning that there's no edge between vertices i and j.

Constraints:
2 ≤ matrix.length < 10,
matrix[i][j] = matrix[j][i],
matrix[i][i] = -1,
matrix[0].length = matrix.length,
-1 ≤ matrix[i][j] < 100.

[output] integer

Radius of the given graph.

int **visitedMin;

void backTrack(std::vector<std::vector<int>>& matrix, int strt, int node, std::vector<int>& visited , int sum)
{
    
    visited[node] = 1;
    if(visitedMin[strt][node] > sum)
        visitedMin[strt][node] = sum;

    int adj = matrix[node].size();
    for( int i = 0; i < adj; i++)
    {
        if(i == node or visited[i] or matrix[node][i] < 0) continue;
        backTrack(matrix, strt, i, visited, sum + matrix[node][i]);
    }
    visited[node] = 0;
}

int giveMeRadius(std::vector<std::vector<int>> matrix) {
    int len = matrix.size();
    visitedMin = (int **)malloc(sizeof(int*)*len);
    for( int i = 0; i < len; i++)
    {
        visitedMin[i] = new int[len]();
        for(int j = 0; j < len; j++)
        {
            visitedMin[i][j] = INT_MAX;
        }
    }
    std::vector<int> visited(len, 0);
    for(int i = 0; i < len; i++)
    {
        visited[i] = 1;
        for(int j = 0; j < len; j++)
        {
            if(matrix[i][j] == -1) continue;
            backTrack(matrix, i, j, visited, matrix[i][j]);
        }
        visited[i] = 0;
    }
    std::vector<int> maxi(len, 0);
    for(int i = 0 ; i < len; i++)
    {
        for(int j = 0; j < len; j++)
        {
            if(visitedMin[i][j] != INT_MAX and maxi[i] < visitedMin[i][j])
            {
                maxi[i] = visitedMin[i][j];
            }
        }
    }
    int mini = INT_MAX;
    for(int i = 0 ; i < len; i++)
    {
        if(mini > maxi[i])
        {
            mini = maxi[i];
        }
    }
    return mini;
}

