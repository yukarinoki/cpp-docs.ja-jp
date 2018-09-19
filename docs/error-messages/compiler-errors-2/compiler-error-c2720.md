---
title: コンパイラ エラー C2720 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2720
dev_langs:
- C++
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2d75c9847016102d4ae8609fb0a0a78726e4c67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084017"
---
# <a name="compiler-error-c2720"></a>コンパイラ エラー C2720

> '*識別子*':'*指定子*' ストレージ クラス指定子のメンバーが無効です

ストレージ クラスは、宣言の外側のクラス メンバーに対して使用することはできません。 このエラーを修正するには、不要な削除[ストレージ クラス](../../cpp/storage-classes-cpp.md)クラス宣言の外側にあるメンバーの定義からの指定子。

## <a name="example"></a>例

次の例では、C2720 を生成し、その修正方法を示しています。

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```