---
description: '詳細情報: ASSERT に代わる VERIFY の使用'
title: ASSERT に代わる VERIFY の使用
ms.date: 05/06/2019
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: cbb878e9184536a6888b84f7861a3e8b7b9ab2b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199052"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT に代わる VERIFY の使用

MFC アプリケーションのデバッグ バージョンを実行したときに、問題がなかったとします。 ただし、同じアプリケーションのリリース バージョンでは、クラッシュしたり、正しくない結果が返されたり、その他の異常な動作が発生したりする可能性があります。

この問題は、ASSERT ステートメントに重要なコードを配置して、正しく実行されることを確認した場合に発生する可能性があります。 MFC プログラムのリリース ビルドでは ASSERT ステートメントはコメント アウトされるため、リリース ビルドではこのコードは実行されません。

関数呼び出しが成功したことを確認するために ASSERT を使用している場合は、代わりに [VERIFY](../mfc/reference/diagnostic-services.md#verify) を使用することを検討してください。 VERIFY マクロでは、アプリケーションのデバッグ ビルドとリリース ビルドの両方で、独自の引数が評価されます。

別の推奨される方法は、関数の戻り値を一時変数に割り当ててから、その変数を ASSERT ステートメントでテストすることです。

次のコード フラグメントがあるとします。

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

MFC アプリケーションのデバッグ バージョンでは、このコードは問題なく実行されます。 `calloc( )` の呼び出しが失敗した場合は、ファイルと行番号を含む診断メッセージが表示されます。 ただし、MFC アプリケーションの製品版ビルドでは次のようになります。

- `calloc( )` の呼び出しは行われず、`buf` は未初期化のままになります。または

- `strcpy_s( )` によって "`Hello, World`" がランダムにメモリにコピーされ、アプリケーションがクラッシュしたり、システムが応答しなくなったりする可能性があります。または

- `free()` によって、割り当てられなかったメモリの解放が試行されます。

ASSERT を正しく使用するには、コード サンプルを次のように変更する必要があります。

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

または、代わりに VERIFY を使用できます。

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](fixing-release-build-problems.md)
