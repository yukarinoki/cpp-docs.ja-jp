---
description: 詳細については、「コンパイラエラー C2813」を参照してください。
title: コンパイラ エラー C2813
ms.date: 11/04/2016
f1_keywords:
- C2813
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 51de4100da8c0dd1a3b2ad1857799769b2abea24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278403"
---
# <a name="compiler-error-c2813"></a>コンパイラ エラー C2813

\#インポートは/MP でサポートされていません

C2813 は、コンパイラのコマンドで **/MP** コンパイラ オプションとコンパイルする 2 つ以上のファイルを指定し、1 つ以上のファイルに [#import](../../preprocessor/hash-import-directive-cpp.md) プリプロセッサ ディレクティブが含まれている場合に生成されます。 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブによって、指定したタイプ ライブラリ内の型から C++ クラスが生成され、これらのクラスが 2 つのヘッダー ファイルに書き込まれます。 複数のコンパイル単位で同じタイプ ライブラリがインポートされる場合、それらの単位は同時に同じヘッダー ファイルに書き込もうとすると競合するため、 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブはサポートされていません。

このコンパイラエラーと **/mp** コンパイラオプションは、Visual Studio 2008 で新たに追加されました。

## <a name="example"></a>例

次の例では C2813 が生成されます。 "compile with:" コメントのコマンド ラインは、 **/MP** および **/c** コンパイラ オプションを使用して複数のファイルをコンパイルすることをコンパイラに示します。 少なくとも 1 つのファイルに [#import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブが含まれています。 この例のテストのために、同じファイルを 2 回使用します。

```cpp
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```
