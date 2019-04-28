---
title: コンパイラ エラー C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: ae416d68831d1964c89d938dfcddd364e521195c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328865"
---
# <a name="compiler-error-c3381"></a>コンパイラ エラー C3381

'アセンブリ' : アセンブリ アクセス指定子は、/clr オプションと共にコンパイルされたコードでのみ使用できます

ネイティブ型をアセンブリ外部から参照できることができますでのネイティブ型のアセンブリへのアクセスのみを指定できます、 **/clr**コンパイルします。

詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)します。

## <a name="example"></a>例

次の例では、C3381 が生成されます。

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```