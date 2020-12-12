---
description: 詳細については、「リンカーツールの警告 LNK4224」を参照してください。
title: リンカー ツールの警告 LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 35cae5c46b91493a40d4d52650f781010f6d6379
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327914"
---
# <a name="linker-tools-warning-lnk4224"></a>リンカー ツールの警告 LNK4224

> *オプション* はサポートされなくなりました。無効

## <a name="remarks"></a>解説

無効な古いリンカーオプションが指定されましたが、無視されました。

たとえば、/comment ディレクティブが .obj に存在する場合、LNK4224 が発生する可能性があります。/Comment ディレクティブは、deprecated exestr オプションを使用して、 [comment (C/c + +)](../../preprocessor/comment-c-cpp.md) プラグマによって追加されています。 .Obj ファイル内のリンカーディレクティブを表示するには、dumpbin [/all](../../build/reference/all.md) を使用します。

可能であれば、.obj のソースを変更し、プラグマを削除します。 この警告を無視すると、 **/clr: pure** を指定してコンパイルされた実行可能ファイルが想定どおりに動作しなくなる可能性があります。 **/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

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
