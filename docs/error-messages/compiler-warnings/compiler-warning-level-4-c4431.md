---
title: コンパイラの警告 (レベル 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: 1cef70ab02148924bf6a0f29e298b34c54b28bc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391518"
---
# <a name="compiler-warning-level-4-c4431"></a>コンパイラの警告 (レベル 4) C4431

型指定子がありません - int と仮定しました。 メモ:C は、int を既定値をサポートしていません

このエラーはビジュアルで行ったコンパイラ準拠作業の結果として生成されるC++2005。VisualC++されなくを既定では int として型指定されていない識別子を作成します。 識別子の型を明示的に指定する必要があります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C4431 が生成されます。

```
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```