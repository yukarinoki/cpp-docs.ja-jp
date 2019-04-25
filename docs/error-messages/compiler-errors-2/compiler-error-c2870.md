---
title: コンパイラ エラー C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165044"
---
# <a name="compiler-error-c2870"></a>コンパイラ エラー C2870

'name': 名前空間の定義がファイル スコープで、または別の名前空間定義内ですぐに表示する必要があります

名前空間を定義した`name`が正しくないです。 (すべてのブロックとクラス) の外部のファイル スコープで名前空間を定義する必要がありますまたは別の名前空間内ですぐにします。

次の例では、C2870 が生成されます。

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```