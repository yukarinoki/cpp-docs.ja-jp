---
title: コンパイラ エラー C2813
ms.date: 11/04/2016
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: 38b4bad77f836053f86a06491ef6bebbcc16671a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265985"
---
# <a name="compiler-error-c2813"></a>コンパイラ エラー C2813

\#インポートは/MP でサポートされていません

C2813 は、コンパイラのコマンドで **/MP** コンパイラ オプションとコンパイルする 2 つ以上のファイルを指定し、1 つ以上のファイルに[#import](../../preprocessor/hash-import-directive-cpp.md) プリプロセッサ ディレクティブが含まれている場合に生成されます。 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブによって、指定したタイプ ライブラリ内の型から C++ クラスが生成され、これらのクラスが 2 つのヘッダー ファイルに書き込まれます。 複数のコンパイル単位で同じタイプ ライブラリがインポートされる場合、それらの単位は同時に同じヘッダー ファイルに書き込もうとすると競合するため、 [#Import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブはサポートされていません。

このコンパイラ エラーと **/MP**コンパイラ オプションは Visual Studio 2008 の新機能です。

## <a name="example"></a>例

次の例では C2813 が生成されます。 "compile with:" コメントのコマンド ラインは、 **/MP** および **/c** コンパイラ オプションを使用して複数のファイルをコンパイルすることをコンパイラに示します。 少なくとも 1 つのファイルに [#import](../../preprocessor/hash-import-directive-cpp.md) ディレクティブが含まれています。 この例のテストのために、同じファイルを 2 回使用します。

```
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```