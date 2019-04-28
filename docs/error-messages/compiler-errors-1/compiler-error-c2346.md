---
title: コンパイラ エラー C2346
ms.date: 11/04/2016
f1_keywords:
- C2346
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
ms.openlocfilehash: a6d75ca671e22203cb40ca18de21606834eeefa8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188092"
---
# <a name="compiler-error-c2346"></a>コンパイラ エラー C2346

'function' は、ネイティブとしてコンパイルできません: 理由

コンパイラは、MSIL に関数をコンパイルできませんでした。

詳細については、次を参照してください。[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)します。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. MSIL にコンパイルできない関数でコードを削除します。

1. 使用して、モジュールがコンパイルされませんか **/clr**、またはアンマネージドのプラグマでアンマネージ関数をマークします。

## <a name="example"></a>例

次の例では、C2346 が生成されます。

```
// C2346.cpp
// processor: x86
// compile with: /clr
// C2346 expected
struct S
{
   S()
   {
      { __asm { nop } }
   }
   virtual __clrcall ~S() { }
};

void main()
{
   S s;
}
```