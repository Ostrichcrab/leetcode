```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    vector<vector<int>> a;
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) {
        if(!root)
            return a;
        
        lot(root,0);
        
        for(int i=0;i<a.size();i++)
            if(i%2)
                reverse(a[i].begin(),a[i].end());
        return a;
    }
    void lot(TreeNode* node, int level)
    {
        if(!node)
            return;
        if(a.size()<level+1)
        {
            vector<int> v1;
            v1.push_back(node->val);
            a.push_back(v1);
        }
        else
            a[level].push_back(node->val);
        
        
            lot(node->left,level+1);
            lot(node->right,level+1);
        
    }
};
```
