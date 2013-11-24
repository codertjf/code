#include <cstdio>
#include <deque>
#include <set>
#include <string>
#include <map>
#include <vector>
#include <cstring>
#include <iostream>
#include <algorithm>
#include <cmath>
#include <queue>
using namespace std;
typedef long long LL;

#define Debug(x) (cerr << #x << " = " << (x) << endl)
#define Debug2(x, y) (cerr << #x << " = " << (x) << ", " << #y << " = " << (y) << endl)
template<class T> inline T& RD(T &x){  
    char c; for (c = getchar(); c < '0'; c = getchar()); x = c - '0'; for (c = getchar(); '0' <= c && c <= '9'; c = getchar()) x = x * 10 + c - '0';  
    return x;  
}


const int inf = 0x3f3f3f3f;
const int maxn = 1001;


//vector<int> g[maxn];
int g[maxn][maxn];
bool used[maxn];
int dist[maxn];
priority_queue<pair<int,int>, vector<pair<int,int> > ,greater<pair<int,int> > > q;
int Dijkstra(int s,int e){
	
	memset(used,false,sizeof(used));
	memset(dist,0x3f,sizeof(dist));
	while(!q.empty())q.pop();

	dist[s] = 0;
	q.push(make_pair(0,s));

	while(!q.empty()){	
		int u = q.top().second;
		int tt = q.top().first;
		
		if(u == e){
			return tt;
		}
		q.pop();
		if(used[u] == false){

			used[u] = true;
			for(int v=1;v<=e;v++){
				if(!used[v] && dist[u]+g[u][v] < dist[v]){
					dist[v] = dist[u] + g[u][v];
					q.push(make_pair(dist[v],v));
				}
			}
		}
	}
	return dist[e];
}



int main(){
	//Dijkstra(1);
	int n,m;
	while(~scanf("%d%d",&n,&m)){

		memset(g,0x3f,sizeof(g));

		for(int i=0;i<m;i++){
			int a,b,c;
			scanf("%d%d%d",&a,&b,&c);
			g[a][b] = c;
		}
		
		int ans = Dijkstra(1,n);
		if(ans >= inf)ans = -1;
		printf("%d\n", ans);
	}	
}
