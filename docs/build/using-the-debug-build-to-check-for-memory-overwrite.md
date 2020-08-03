---
title: デバッグ ビルドを使用したメモリ上書きのチェック
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 152f72749d2ebdacd46dd3e4db671bc5705d4b6a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213750"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>デバッグ ビルドを使用したメモリ上書きのチェック

デバッグ ビルドを使用してメモリ上書きをチェックするには、まずデバッグ用にプロジェクトをリビルドする必要があります。 次に、アプリケーションの `InitInstance` 関数の先頭に移動して、次の行を追加します。

```
afxMemDF |= checkAlwaysMemDF;
```

デバッグ メモリ アロケーターによって、すべてのメモリ割り当ての周りにガード バイトが配置されます。 ただし、このようなガード バイトは、変更されている (メモリの上書きが示されている) かどうかをチェックしない限り、役に立ちません。 そうでなければ、実際のところ、これはメモリの上書きを回避できる可能性がある単なるバッファーです。

`checkAlwaysMemDF` を有効にすると、 **`new`** または **`delete`** が呼び出されるたびに `AfxCheckMemory` 関数を呼び出すように MFC に強制することになります。 メモリの上書きが検出された場合、次のような TRACE メッセージが生成されます。

```
Damage Occurred! Block=0x5533
```

これらのメッセージのいずれかが表示された場合は、コードをステップ実行して、破損が発生した場所を特定する必要があります。 メモリの上書きが発生した場所をより正確に特定するには、`AfxCheckMemory` を明示的に呼び出します。 次に例を示します。

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

最初の ASSERT が成功し、2 番目の ASSERT が失敗する場合は、2 つの呼び出しの間の関数でメモリの上書きが発生しているはずです。

アプリケーションの性質によっては、`afxMemDF` が原因でプログラムの実行が非常に遅くなり、テストすらできなくなる場合があります。 `afxMemDF` 変数を使用すると、new および delete を呼び出すたびに `AfxCheckMemory` が呼び出されます。 そのような場合は、上記のように `AfxCheckMemory`() の呼び出しを分散して使用し、メモリの上書きを特定してみてください。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](fixing-release-build-problems.md)
