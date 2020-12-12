---
description: '詳細情報: 致命的なエラー C1190'
title: 致命的なエラー C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: e351a04d548816999d61973276203d34745c0a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123605"
---
# <a name="fatal-error-c1190"></a>致命的なエラー C1190

マネージド ターゲット コードには '/clr' が必要です。

CLR コンストラクトを使用していますが、 **/clr** を指定していませんでした。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

次の例では C1190 が生成されます。

```cpp
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```
