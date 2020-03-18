---
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
ms.openlocfilehash: bfc0847677ae232fef67ab6200c626472f042bdb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438612"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT に代わる VERIFY の使用

MFC アプリケーションのデバッグバージョンを実行しても問題がないとします。 ただし、同じアプリケーションのリリースバージョンがクラッシュしたり、正しくない結果が返されたり、その他の異常な動作が発生したりする可能性があります。

この問題は、ASSERT ステートメントに重要なコードを配置して、正しく実行されることを確認した場合に発生する可能性があります。 ASSERT ステートメントは、MFC プログラムのリリースビルドでコメントアウトされているため、コードはリリースビルドでは実行されません。

ASSERT を使用して関数呼び出しが成功したことを確認する場合は、代わりに VERIFY を使用する[こと](../mfc/reference/diagnostic-services.md#verify)を検討してください。 VERIFY マクロは、アプリケーションのデバッグビルドとリリースビルドの両方で、独自の引数を評価します。

もう1つの推奨される方法は、関数の戻り値を一時変数に割り当て、ASSERT ステートメントで変数をテストすることです。

次のコードを確認します。

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

このコードは、MFC アプリケーションのデバッグバージョンでは完全に実行されます。 `calloc( )` の呼び出しが失敗した場合は、ファイルと行番号を含む診断メッセージが表示されます。 ただし、MFC アプリケーションの製品版ビルドでは、次のようになります。

- `calloc( )` の呼び出しは行われず `buf` 未初期化のままになります。

- `strcpy_s( )` は、"`Hello, World`" をランダムなメモリにコピーします。アプリケーションがクラッシュしたり、システムが応答しなくなったりする可能性があります。

- `free()` は、割り当てられていないメモリの解放を試みます。

ASSERT を正しく使用するには、コードサンプルを次のように変更する必要があります。

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

## <a name="see-also"></a>参照

[リリース ビルドの問題の解決](fixing-release-build-problems.md)
