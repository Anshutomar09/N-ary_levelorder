# N-ary_levelorder

class Solution {
public:
    vector<vector<int>> levelOrder(Node* root) {
        vector<vector<int>>ans;
        queue<Node*>q;
        q.push(root);
        if(root==NULL){
            return ans;
        }
        while(1){
            int size=q.size();
            if(size==0){
                return ans;
            }
            vector<int>data;
            while(size>0){
                Node* temp=q.front();
                q.pop();
                data.push_back(temp->val);
                for (Node*& child: temp->children) {
                    q.push(child);
                }
                
                size--;
            }
            
            ans.push_back(data);
        }
        return ans;
        
    }
};
