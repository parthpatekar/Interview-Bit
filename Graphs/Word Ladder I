bool isValid(string a, string b){
    int c=0;
    for(int i=0;i<a.length();i++){
        if(a[i]!=b[i])
            c++;
    }
    return c==1 ? 1 : 0;
}

int Solution::ladderLength(string start, string end, vector<string> &dictV) {
    // Do not write main() function.
    // Do not read input, instead use the arguments to the function.
    // Do not print the output, instead return values as specified
    // Still have a doubt. Checkout www.interviewbit.com/pages/sample_codes/ for more details
    if(dictV.size()==2){
        if(dictV[0]==dictV[1])
            return 1;
        else if(isValid(dictV[0], dictV[1]))
            return 2;
        else
            return 0;
    }
    queue<pair<string, int> > q;
    bool visited[dictV.size()];
    memset(visited, 0, sizeof(visited));
    pair<string, int> item=make_pair(start, 1);
    q.push(item);
    while(!q.empty()){
        pair<string, int> curr=q.front();
        q.pop();
        for(int i=0;i<dictV.size();i++){
            if(isValid(curr.first, dictV[i]) && !visited[i]){
                item.first=dictV[i];
                item.second=curr.second+1;
                q.push(item);
                visited[i]=1;
                if(dictV[i]==end)
                    return item.second;
            }
        }
    }
    return 0;
}
