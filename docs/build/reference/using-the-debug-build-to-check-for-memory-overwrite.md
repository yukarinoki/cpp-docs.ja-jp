---
title: チェックするデバッグ ビルドを使用したメモリ上書き |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96afeb6be9aac754c952824716322c55d4819d6e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706356"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>デバッグ ビルドを使用したメモリ上書きのチェック

デバッグ ビルドを使用すると、メモリの上書きを確認して、最初にプロジェクトをデバッグを再構築する必要があります。 アプリケーションの先頭に移動し、`InitInstance`関数を次の行を追加します。

```
afxMemDF |= checkAlwaysMemDF;
```

デバッグ メモリ アロケーターは、すべてのメモリ割り当ての周囲のガード バイトを書き込みます。 ただし、これらのガード バイトかどうか変更されている (つまり、メモリの上書き) をチェックする場合を除き、役に立つを行わない。 それ以外の場合、これだけバッファーを提供する可能性があります、実際には、メモリの上書きを回避します。

オンにして、 `checkAlwaysMemDF`、MFC への呼び出しを行うには強制は、`AfxCheckMemory`関数への呼び出しのたびに**新しい**または**削除**されます。 メモリの上書きが検出された場合は、次のようなトレース メッセージが生成されます。

```
Damage Occurred! Block=0x5533
```

これらのメッセージのいずれかを表示する場合は、破損が発生したかを判断するコードをステップ実行する必要があります。 具体的には、メモリの上書きが発生した場所を特定するには、明示的な呼び出しを行うことができます`AfxCheckMemory`自分でします。 例えば:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

最初のアサートが成功すると、2 つ目が失敗して場合、は、2 つの呼び出しの間での関数でメモリの上書きが発生したことを意味します。

によって、アプリケーションの性質なことがわかります`afxMemDF`テストも実行速度が、プログラムが原因です。 `afxMemDF`変数`AfxCheckMemory`を新しい呼び出しのたびに呼び出され、削除します。 その場合は、呼び出しを散布する必要があります`AfxCheckMemory`、上記のように () とメモリを特定することを上書きします。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)