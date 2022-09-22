## GROUP BY로 MIN과MAX 사용하기

* COUNT와 GROUP BY를 사용하는것과 유사함

```sql
SELECT author_fname, author_lname, MIN(released_year) FROM books GROUP BY author_lname, author_fname;
+--------------+----------------+--------------------+
| author_fname | author_lname   | MIN(released_year) |
+--------------+----------------+--------------------+
| Raymond      | Carver         |               1981 |
| Michael      | Chabon         |               2000 |
| Don          | DeLillo        |               1985 |
| Dave         | Eggers         |               2001 |
| David        | Foster Wallace |               2004 |
| Neil         | Gaiman         |               2001 |
| Dan          | Harris         |               2014

SELECT author_fname, author_lname, MIN(pages) FROM books GROUP BY author_lname, author_fname;
+--------------+----------------+------------+
| author_fname | author_lname   | MIN(pages) |
+--------------+----------------+------------+
| Raymond      | Carver         |        176 |
| Michael      | Chabon         |        634 |
| Don          | DeLillo        |        320 |
| Dave         | Eggers         |        352 |

SELECT released_year, COUNT(released_year) AS count FROM books GROUP BY released_year ORDER BY count DESC
LIMIT 1;
+---------------+-------+
| released_year | count |
+---------------+-------+
|          2001 |     3 |
+---------------+-------+
```
