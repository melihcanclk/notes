# Spring Transactions Like A Hero

> Bu Notlar Hüseyin Babal'ın [Spring Transactions Like A Hero](https://youtu.be/uTG952A6KBY) videosundan alınmıştır.

![What is Transaction](images/spring-transactions-like-a-hero/1.png)

![What is Rollback](images/spring-transactions-like-a-hero/2.png)

![What is Spring Transaction](images/spring-transactions-like-a-hero/3.png)

Spring, eğer bir methodun üzerine `@Transactional` annotation'ı koyarsak, o method için bir proxy oluşturur.

> Spring, Byte manipulation ve Reflection’u kullanarak yapıyor.

> Spring, private mehtod'larda transactional annotation'ı desteklemiyor. Örnek olarak yukarıda tanımlanmış olan `create` method'unu ele alırsak,
> `create` method'u `@Transactional` annotation'ı ile işaretlenmiş olsa bile, `create` method'u eğer aynı class içerisinde başka bir methodu çağırıyorsa
> ve çağırılan method `@Transactional` annotation'ı ile işaretlenmiş olsa bile, çağırılan method transactional olarak çalışmayacaktır. Bunun sebebi
> Spring'in private method'larda transactional annotation'ı desteklememesidir.

![Transaction Propagation](images/spring-transactions-like-a-hero/4.png)

Transaction Propagation, herhangi bir component'in veya servisin işleme katılıp katılmayacağını belirtir. Ayrıca, arayan component'in veya servisin halihazırda oluşturulmuş bir işlemi olup olmadığı durumunda nasıl davranacağını da gösterir.

Propagation Tipleri:

![REQUIRED](images/spring-transactions-like-a-hero/required.png)

![SUPPORTS](images/spring-transactions-like-a-hero/supports.png)

![NOT_SUPPORTED](images/spring-transactions-like-a-hero/not_supported.png)

![REQUIRES_NEW](images/spring-transactions-like-a-hero/requires_new.png)

![MANDATORY](images/spring-transactions-like-a-hero/mandatory.png)

![NEVER](images/spring-transactions-like-a-hero/never.png)

Transaction'daki Isolation Seviyeleri:

- Dirty Read
- Non-Repeatable Read
- Phantom Read

|          Dirty Read           |               Non-Repeatable Read               |           Phantom Read            |
| :---------------------------: | :---------------------------------------------: | :-------------------------------: |
| ![Dirty Read](images/spring-transactions-like-a-hero/dirty_read.png) | ![Non-Repeatable Read](images/spring-transactions-like-a-hero/non_repeatable_read.png) | ![Phantom Read](images/spring-transactions-like-a-hero/phantom_read.png) |

Spring Isolation Seviyeleri:

- ISOLATION_READ_UNCOMMITTED
- ISOLATION_READ_COMMITTED
- ISOLATION_REPEATABLE_READ
- ISOLATION_SERIALIZABLE

![ISOLATION_READ_UNCOMMITTED](images/spring-transactions-like-a-hero/isolation_read_uncommitted.png)
![ISOLATION_READ_COMMITTED](images/spring-transactions-like-a-hero/isolation_read_committed.png)
![ISOLATION_REPEATABLE_READ](images/spring-transactions-like-a-hero/isolation_repeatable_read.png)
![ISOLATION_SERIALIZABLE](images/spring-transactions-like-a-hero/isolation_serializable.png)

Video içerisindeki kod örneklerine [buradan](https://youtu.be/uTG952A6KBY?t=2727) ulaşabilirsiniz. Çok uzun olduğu için buraya eklemek istemedim.
