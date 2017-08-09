# 修改 Store 中的数据


```diff
--- a/src/components/CommentBox.vue
+++ b/src/components/CommentBox.vue
@@ -13,6 +13,8 @@
 </template>

 <script>
+  import * as types from '../store/mutation-types'
+
   export default {
     name: 'comment-box',
     data: () => ({
@@ -29,9 +31,7 @@
       addComment () {
         const input = document.getElementById('commentForm')
         if (input.value !== '') {
-          this.comments.push({
-            content: input.value
-          })
+          this.$store.commit(types.ADD_COMMENT, { content: input.value })
           input.value = ''
         }
       }
```


```diff
--- a/src/store/modules/comment.js
+++ b/src/store/modules/comment.js
@@ -1,3 +1,5 @@
+import * as types from '../mutation-types'
+
 const state = {
   all: [
     { content: 'fooo' },
@@ -5,6 +7,13 @@ const state = {
   ]
 }

+const mutations = {
+  [types.ADD_COMMENT] (state, { content }) {
+    state.all.push({ content })
+  }
+}
+
 export default {
-  state
+  state,
+  mutations
 }
```
