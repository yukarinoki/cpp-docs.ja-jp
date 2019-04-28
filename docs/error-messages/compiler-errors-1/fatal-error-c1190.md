---
title: 致命的なエラー C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228906"
---
# <a name="fatal-error-c1190"></a>致命的なエラー C1190

マネージド ターゲット コードには '/clr' が必要です。

CLR コンストラクトを使用していますが、 **/clr**を指定していませんでした。

詳細については、「 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

次の例では C1190 が生成されます。

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```