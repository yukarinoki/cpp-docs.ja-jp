---
title: リンカー ツールの警告 LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 9e52dd533d897e729aba5f2b43ea6c019a024d43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182982"
---
# <a name="linker-tools-warning-lnk4224"></a>リンカー ツールの警告 LNK4224

> *オプション*はサポートされなくなりました。無効

## <a name="remarks"></a>解説

無効な古いリンカーオプションが指定されましたが、無視されました。

たとえば、/comment ディレクティブが .obj に存在する場合、LNK4224 が発生する可能性があります。/Comment ディレクティブは、deprecated exestr オプションを使用して、 [commentC++(C/)](../../preprocessor/comment-c-cpp.md)プラグマを通じて追加されています。 .Obj ファイル内のリンカーディレクティブを表示するには、dumpbin [/all](../../build/reference/all.md)を使用します。

可能であれば、.obj のソースを変更し、プラグマを削除します。 この警告を無視すると、 **/clr: pure**を指定してコンパイルされた実行可能ファイルが想定どおりに動作しなくなる可能性があります。 **/Clr: pure**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

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
