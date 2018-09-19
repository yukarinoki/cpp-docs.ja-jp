---
title: コンパイラ エラー C2346 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec916bcdce1a43c597d8cfae10e5393cbeb99ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108615"
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