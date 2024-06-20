#include <stdio.h>
#define V 4
int graph[V][V] = {
    {0, 10, 15, 20},
    {10, 0, 35, 25},
    {15, 35, 0, 30},
    {20, 25, 30, 0}
};
int VISITED_ALL = (1 << V) - 1;
int tsp(int mask, int pos) {
    if (mask == VISITED_ALL) {
        return graph[pos][0];
    }
    int min_cost = 99999;
    for (int city = 0; city < V; city++) {
        if ((mask & (1 << city)) == 0) {
            int new_cost = graph[pos][city] + tsp(mask | (1 << city), city);
            if (new_cost < min_cost) {
                min_cost = new_cost;
            }
        }
    }
    return min_cost;
}
int main() {
    int mask = 1;
    int pos = 0;
    printf("The minimum cost of the Travelling Salesman Problem is: %d\n", tsp(mask, pos));
    return 0;
}
