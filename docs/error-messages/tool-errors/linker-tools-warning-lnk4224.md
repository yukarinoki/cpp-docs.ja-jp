---
title: リンカー ツールの警告 LNK4224 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bdffdf3469cc3a0e5d41b0504b882513d44b63c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703988"
---
# <a name="linker-tools-warning-lnk4224"></a>リンカー ツールの警告 LNK4224

> *オプション*はサポートされていません無視されます。

## <a name="remarks"></a>コメント

無効な古いリンカー オプションが指定され、無視されます。

たとえば、LNK4224 発生する可能性が/comment ディレクティブが表示される場合 .obj。使用して追加されて、/comment ディレクティブ、[コメント (C/C++)](../../preprocessor/comment-c-cpp.md)プラグマによって、非推奨 exestr オプションを使用します。 Dumpbin を使用して[/all](../../build/reference/all.md)を .obj ファイル内のリンカー ディレクティブを表示します。

可能であれば、.obj ファイルのソースを変更し、このプラグマを削除します。 この警告を無視すると場合、.executable コンパイルされている可能性が **/clr: 純粋な**期待どおりに実行されません。 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

## <a name="example"></a>例

次の例では、LNK4224 が生成されます。

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```