---
title: コンパイラエラー C2705
description: Microsoft C/c + + コンパイラエラー C2705 について説明します。
ms.date: 08/25/2020
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 40d0f70ee379f5d1347b7443817713a53e097f89
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898750"
---
# <a name="compiler-error-c2705"></a>コンパイラエラー C2705

> '*label*': ' exception handler block ' スコープへのジャンプが正しくありません。

## <a name="remarks"></a>注釈

実行は **`try`** / **`catch`** 、、 **`__try`** / **`__except`** 、または **`__try`** / **`__finally`** ブロック内のラベルにジャンプします。 コンパイラでは、この動作は許可されていません。 詳細については、「 [例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C2705 が生成されます。

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
