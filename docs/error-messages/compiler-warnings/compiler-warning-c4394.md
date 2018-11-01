---
title: コンパイラの警告 C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548852"
---
# <a name="compiler-warning-c4394"></a>コンパイラの警告 C4394

'関数' : appdomain ごとのシンボルは __declspec(dllexport) と共に設定することはできません

マークされた関数、 [appdomain](../../cpp/appdomain.md) `__declspec`にではなくネイティブ)、MSIL とエクスポート テーブルにコンパイルされ、修飾子 ([エクスポート](../../windows/export.md)`__declspec`修飾子) はマネージ関数のサポートされていません。

public アクセシビリティを持つようにマネージド関数を宣言できます。 詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)と[メンバーの可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)します。

C4394 は、常にエラーとして表示されます。  この警告をオフにすることができます、`#pragma warning`または **/wd**; を参照してください[警告](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//we、/wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C4394 が生成されます。

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```