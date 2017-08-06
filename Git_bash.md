# Git���������ܽ�

## git init
     �ڱ����½�һ��repo,����һ����ĿĿ¼,ִ��git init,���ʼ��һ��repo,���ڵ�ǰ�ļ����´���һ��.git�ļ���.
 
## git clone
     ��ȡһ��url��Ӧ��Զ��Git repo, ����һ��local copy.
     һ��ĸ�ʽ��git clone [url].
     clone������repo����url���һ��б�ߺ������������,����һ���ļ���,�����Ҫָ���ض�������,����git clone [url] newnameָ��.
 
## git status
     ��ѯrepo��״̬.
     git status -s: -s��ʾshort, -s�������ǻ�������,��һ���Ƕ�staging�������,�ڶ����Ƕ�workingĿ¼����.
 
## git log
     show commit history of a branch.
     git log --oneline --number: ÿ��logֻ��ʾһ��,��ʾnumber��.
     git log --oneline --graph:����ͼ�λ��ر�ʾ����֧�ϲ���ʷ.
     git log branchname������ʾ�ض���֧��log.
     git log --oneline branch1 ^branch2,���Բ鿴�ڷ�֧1,ȴ���ڷ�֧2�е��ύ.^��ʾ�ų������֧(Window�¿���Ҫ��^branch2��������).
     git log --decorate����ʾ��tag��Ϣ.
     git log --author=[author name] ����ָ�����ߵ��ύ��ʷ.
     git log --since --before --until --after �����ύʱ��ɸѡlog.
     --no-merges���Խ�merge��commits�ų�����.
     git log --grep ����commit��Ϣ����log: git log --grep=keywords
     Ĭ�������, git log --grep --author��OR�Ĺ�ϵ,������һ����������,���������������AND�Ĺ�ϵ,���Լ���--all-match��option.
     git log -S: filter by introduced diff.
     ����: git log -SmethodName (ע��S�ͺ���Ĵ�֮��û�еȺŷָ�).
     git log -p: show patch introduced at each commit.
     ÿһ���ύ����һ������(snapshot),Git���ÿ���ύ��diff�������,��Ϊһ��patch��ʾ���㿴.
     ��һ�ַ�����git show [SHA].
     git log --stat: show diffstat of changes introduced at each commit.
     ͬ�����������Ķ��������Ϣ��,--stat��-p���������һЩ.
    
## git add
     ���ύ֮ǰ,Git��һ���ݴ���(staging area),���Է��������ӵ��ļ����߼����µĸĶ�. commitʱ�ύ�ĸĶ�����һ�μ��뵽staging area�еĸĶ�,����������disk�ϵĸĶ�.
     git add .
     ��ݹ�����ӵ�ǰ����Ŀ¼�е������ļ�.
 
## git diff
     ���Ӳ�����git diff:
     show diff of unstaged changes.
     ������Ƚϵ��ǹ���Ŀ¼�е�ǰ�ļ����ݴ��������֮��Ĳ���,Ҳ�����޸�֮��û���ݴ������ı仯����.
 
     ��Ҫ���Ѿ��ݴ��������ļ����ϴ��ύʱ�Ŀ���֮��Ĳ���,������:
     git diff --cached ����.
     show diff of staged changes.
     (Git 1.6.1 �����߰汾������ʹ�� git diff --staged��Ч������ͬ��).
 
     git diff HEAD
     show diff of all staged or unstated changes.
     Ҳ���Ƚ�woking directory���ϴ��ύ֮�����еĸĶ�.
 
     ����뿴�Դ�ĳ���汾֮�󶼸Ķ���ʲô,������:
     git diff [version tag]
     ��log����һ��,diffҲ���Լ���--stat�����������.
 
     git diff [branchA] [branchB]���������Ƚ�������֧.
     ��ʵ���ϻ᷵��һ����A��B��patch,����������Ҫ�Ľ��.
     һ��������Ҫ�Ľ����������֧�ֿ��Ժ���ԵĸĶ�����ʲô,��������:
     git diff [branchA]��[branchB]������.
     ʵ��������:git diff $(git merge-base [branchA] [branchB]) [branchB]�Ľ��.
 
 
## git commit
     �ύ�Ѿ���add�����ĸĶ�.
     git commit -m ��the commit message"
     git commit -a ���Ȱ������Ѿ�track���ļ��ĸĶ�add����,Ȼ���ύ(�е���svn��һ���ύ,�������ݴ�). ����û��track���ļ�,������Ҫgit addһ��.
     git commit --amend �����ύ. ��ʹ���뵱ǰ�ύ�ڵ���ͬ�ĸ��ڵ����һ���µ��ύ,�ɵ��ύ���ᱻȡ��.
 
## git reset
     undo changes and commits.
     �����HEAD�ؼ���ָ���ǵ�ǰ��֧��ĩ�����µ�һ���ύ.Ҳ���ǰ汾���и÷�֧�ϵ����°汾.
     git reset HEAD: unstage files from index and reset pointer to HEAD
     ������������Ѳ�С��add��ȥ���ļ���staged״̬ȡ����,���Ե������ĳһ���ļ�����: git reset HEAD - - filename, ���- - Ҳ���Բ���.
     git reset --soft
     move HEAD to specific commit reference, index and staging are untouched.
     git reset --hard
     unstage files AND undo any changes in the working directory since last commit.
     ʹ��git reset ��hard HEAD����reset,���ϴ��ύ֮��,����staged�ĸĶ��͹���Ŀ¼�ĸĶ�������ʧ,��ԭ���ϴ��ύ��״̬.
     �����HEAD���Ա�д���κ�һ���ύ��SHA-1.
     ����soft��hard������git reset,ʵ���ϴ�����Ĭ�ϲ���mixed.
 
     �ܽ�:
     git reset --mixed id,�ǽ�git��HEAD����(Ҳ�����ύ��¼����),���ļ���û�иı䣬(Ҳ����working tree��û�иı�). ȡ����commit��add������.
     git reset --soft id. ʵ���ϣ���git reset �Cmixed id ��,������һ��git add.��ȡ����commit������.
     git reset --hard id.�ǽ�git��HEAD����,�ļ�Ҳ����.
     ���Ķ���Χ��������:
     soft (commit) < mixed (commit + add) < hard (commit + add + local working)
 
## git revert
     ��ת�����ύ.ֻҪ�ѳ������ύ(commit)������(reference)��Ϊ������������Ϳ�����.
     git revert HEAD: ���������һ���ύ.
     git revert�ᴴ��һ����������ύ,����ͨ������-n������Git�Ȳ�Ҫ�ύ.
    
## git rm
     git rm file: ��staging���Ƴ��ļ�,ͬʱҲ�Ƴ�������Ŀ¼.
     git rm --cached: ��staging���Ƴ��ļ�,�����ڹ���Ŀ¼��.
     git rm --cached�ӹ����ϵ�ͬ��git reset HEAD,����˻�����,����������Ŀ¼��.
 
## git clean
     git clean�Ǵӹ���Ŀ¼���Ƴ�û��track���ļ�.
     ͨ���Ĳ�����git clean -df:
     -d��ʾͬʱ�Ƴ�Ŀ¼,-f��ʾforce,��Ϊ��git�������ļ���, clean.requireForce=true,�������-f,clean����ܾ�ִ��.
 
## git mv
     git rm - - cached orig; mv orig new; git add new
 
## git stash
     �ѵ�ǰ�ĸĶ�ѹ��һ��ջ.
     git stash����ѵ�ǰĿ¼��index�е����иĶ�(��������δtrack���ļ�)ѹ��һ��ջ,Ȼ��������һ��clean�Ĺ���״̬,��������һ�������ύ��.
     git stash list����ʾ���ջ��list.
     git stash apply:ȡ��stash�е���һ����Ŀ(stash@{0}),����Ӧ���ڵ�ǰ�Ĺ���Ŀ¼.
     Ҳ����ָ�������Ŀ,����git stash apply stash@{1}.
     �������Ӧ��stash����Ŀ��ͬʱ��Ҫɾ����,������git stash pop
 
     ɾ��stash�е���Ŀ:
     git stash drop: ɾ����һ��,Ҳ��ָ������ɾ��ָ����һ����Ŀ.
     git stash clear: ɾ��������Ŀ.
 
## git branch
     git branch���������г���֧,������֧��ɾ����֧.
     git branch -v���Կ���ÿһ����֧�����һ���ύ.
     git branch: �г��������з�֧,��ǰ��֧�ᱻ�Ǻű�ʾ��.
     git branch (branchname): ����һ���µķ�֧(���������ַ�ʽ������֧��ʱ��,��֧�ǻ��������һ���ύ������). 
     git branch -d (branchname): ɾ��һ����֧.
     ɾ��remote�ķ�֧:
     git push (remote-name) :(branch-name): delete a remote branch.
     �������Ϊ������������ʽ��:
     git push remote-name local-branch:remote-branch
     ������local-branch�Ĳ���Ϊ��,����ζ��ɾ����remote-branch
 
## git checkout
����git checkout (branchname)   �л���һ����֧.
     git checkout -b (branchname): �������л����µķ�֧.
     ��������ǽ�git branch newbranch��git checkout newbranch����һ��Ľ��.
     checkout������һ������:�滻���ظĶ�:
     git checkout --<filename>
     �������ʹ��HEAD�е����������滻����Ĺ���Ŀ¼�е��ļ�.�����ӵ��ݴ����ĸĶ��Լ����ļ��������ܵ�Ӱ��.
     ע��:git checkout filename��ɾ�����ļ�������û���ݴ���ύ�ĸĶ�,��������ǲ������.
 
## git merge
     ��һ����֧merge����ǰ�ķ�֧.
     git merge [alias]/[branch]
     ��Զ�̷�֧merge����ǰ��֧.
 
     ������ֳ�ͻ,��Ҫ�ֶ��޸�,������git mergetool.
     �����ͻ��ʱ������õ�git diff,�����֮����git add����,����ʾ��ͻ�Ѿ���resolved.
 
## git tag
     tag a point in history as import.
     ����һ���ύ�Ͻ��������Ե���ǩ,ͨ���Ƿ���һ��release�汾����ship��ʲô����֮���tag.
     ����: git tag v1.0
     git tag -a v1.0, -a����������������һЩ��Ϣ,��make an annotated tag.
     ��������git tag -a�����ʱ��,Git���һ���༭����������tag��Ϣ.
     
     ���ǿ�������commit SHA����һ����ȥ���ύ��tag:
     git tag -a v0.9 XXXX
 
     push��ʱ���ǲ�����tag��,��������,������pushʱ����--tags����.
     fetch��ʱ��,branch HEAD����reach��tags���Զ���fetch������, tags that aren��t reachable from branch heads will be skipped.�����ȷ�����е�tags������������,��Ҫ����--tagsѡ��.
 
## git remote
     list, add and delete remote repository aliases.
     ��Ϊ����Ҫÿ�ζ���������url,����GitΪÿһ��remote repo��url������һ������,Ȼ����git remote���������list.
     git remote: �г�remote aliases.
     �����cloneһ��project,Git���Զ���ԭ����url���ӽ���,�����ͽ���:origin.
     git remote -v:���Կ���ÿһ��������Ӧ��ʵ��url.
     git remote add [alias] [url]: ����һ���µ�remote repo.
     git remote rm [alias]: ɾ��һ�����ڵ�remote alias.
     git remote rename [old-alias] [new-alias]: ������.
     git remote set-url [alias] [url]:����url. ���Լ��ϡ�push��fetch����,Ϊͬһ������set��ͬ�Ĵ�ȡ��ַ.
 
## git fetch
     download new branches and data from a remote repository.
     ����git fetch [alias]ȡĳһ��Զ��repo,Ҳ����git fetch --allȡ��ȫ��repo
     fetch����ȡ�������㱾��û�е�����,����ȡ�����ķ�֧���Ա�����remote branches,���Ǻͱ��ط�֧һ��(���Կ�diff,log��,Ҳ����merge��������֧),����Git��������checkout������. 
 
## git pull
     fetch from a remote repo and try to merge into the current branch.
     pull == fetch + merge FETCH_HEAD
     git pull������ִ��git fetch,Ȼ��ִ��git merge,��ȡ���ķ�֧��head merge����ǰ��֧.���merge���������һ���µ�commit.    
     ���ʹ��--rebase����,����ִ��git rebase��ȡ��ԭ����git merge.
  
 
## git rebase
     --rebase��������ϲ����ύ,���Ὣ���ص������ύ��ʱ����Ϊ����(patch),���ڡ�.git/rebase��Ŀ¼��,Ȼ�󽫵�ǰ��֧���µ����µķ�֧���,���ѱ���Ĳ���Ӧ�õ���֧��.
     rebase�Ĺ�����,Ҳ������ֳ�ͻ,Git��ֹͣrebase����������ͻ,�ڽ�����ͻ֮��,��git addȥ������Щ����,Ȼ������ִ��commit,ֻ��Ҫ:
     git rebase --continue�ͻ���������µĲ���.
     git rebase --abort������ֹrebase,��ǰ��֧����ص�rebase֮ǰ��״̬.
 
## git push
     push your new branches and data to a remote repository.
     git push [alias] [branch]
     ����ѵ�ǰ��֧merge��alias�ϵ�[branch]��֧.�����֧�Ѿ�����,�������,���������,�������������֧.
     ����ж������ͬһ��remote repo push����, Git������������ͼpush�ķ�֧������git log,���������ʷ���Ƿ��ܿ���server�ϵ�branch���ڵ�tip,���������ʷ�в��ܿ���server��tip,˵�����صĴ��벻�����µ�,Git��ܾ����push,������fetch,merge,֮����push,�����ͱ�֤�������˵ĸĶ����ᱻ���ǽ���.
 
## git reflog
     git reflog�Ƕ�reflog���й���������,reflog��git������¼���ñ仯��һ�ֻ���,�����¼��֧�ı仯������HEAD���õı仯.
     ��git reflog��ָ�����õ�ʱ��,Ĭ���г�HEAD��reflog.
     HEAD@{0}����HEAD��ǰ��ֵ,HEAD@{3}����HEAD��3�α仯֮ǰ��ֵ.
     git�Ὣ�仯��¼��HEAD��Ӧ��reflog�ļ���,��·��Ϊ.git/logs/HEAD, ��֧��reflog�ļ�������.git/logs/refsĿ¼�µ���Ŀ¼��.
 
 
�������:
     ^�������ύ,��һ���ύ�ж�����ύʱ,����ͨ����^�������һ������,��ʾ�ڼ������ύ: ^�൱��^1.
     ~<n>�൱��������<n>��^.
 
 
 
## �ο�����

http://git-scm.com/book/zh/v1
https://git-scm.com/book/zh/v2