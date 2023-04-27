htmlフォルダ内にsql fileが存在する。
そこにテーブルの作成queryがある。

at first You need to create a todo table because I couldn't implement auto-create-tabel setting in docker-compose.yml.


*tasks that I must work on if I have time.
1. to enable type hinting, upgrade php version.

2 write test codes.

3 When attaching a db container, log in mysql and use a db automatically.

4 if a title is null, exit *add func* process.


# table structure

refer to main.sql

*list session key

refer to session.txt(It is still unimplemented）

# how to enter in docker-container

docker exec -it <container id> /bin/bash

---------------------------------------------------

codeみてておもったんだけど todo.php のupchange もっと短くかけるな。

 $clickTarget = $stm1->fetch(\PDO::FETCH_COLUMN);

    $stm2 = $this->pdo->prepare("SELECT min(pos) FROM todos WHERE pos > (SELECT pos FROM todos WHERE id = :id)");
    
    を
    
    $stm2 = $this->pdo->prepare("SELECT min(pos) FROM todos WHERE pos > $clickTarget");
    
    


When I was reading Todo.php code, I wonder 
