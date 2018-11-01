---
title: あいまいな宣言 (C++) の解決
ms.date: 11/04/2016
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
ms.openlocfilehash: 52e94f474d59505298cb4f78a477cedd21b90aad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507368"
---
# <a name="resolving-ambiguous-declarations-c"></a>あいまいな宣言 (C++) の解決

特定の型から別の型に明示的に変換するには、キャストを使用し、目的の型名を指定する必要があります。 一部の型キャストでは、構文にあいまいさが発生します。 次の関数形式の型キャストはあいまいです。

```cpp
char *aName( String( s ) );
```

関数宣言と関数スタイルの初期化子としてキャストされるオブジェクトの宣言であるか明確ではありません型を返す関数を宣言できます`char *`型の 1 つの引数を受け取る`String`、またはオブジェクトを宣言できます。`aName`しの値で初期化`s`型にキャスト`String`します。

宣言を有効な関数宣言と見なすことができれば、それは関数の宣言として扱われます。 宣言が関数宣言とは考えられない (つまり、関数宣言だとすれば構文的に正しくないと考えられる) 場合にのみ、そのステートメントが関数形式の型キャストかどうかが確認されます。 したがって、コンパイラはこのステートメントを関数の宣言であると見なし、識別子 `s` を囲むかっこを無視します。 一方、次のステートメント、

```cpp
char *aName( (String)s );
```

と、呼び出し

```cpp
char *aName = String( s );
```

オブジェクト、およびユーザー定義型からの変換の宣言では明確に`String`入力`char *`の初期化を実行するために呼び出す`aName`します。