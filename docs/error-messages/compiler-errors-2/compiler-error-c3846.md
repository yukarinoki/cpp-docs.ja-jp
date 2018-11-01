---
title: コンパイラ エラー C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 788f03e4364404ad5c30b7edcba8b743c7f201ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651218"
---
# <a name="compiler-error-c3846"></a>コンパイラ エラー C3846

'symbol': 'assembly2' からシンボルをインポートできません: 'symbol' は、別のアセンブリ 'assembly1' から既にインポートされていますが、

以前に参照されたアセンブリからインポートされたために、参照されたアセンブリからシンボルをインポートできませんでした。

## <a name="example"></a>例

次の例では、C3846 が生成されます。

```
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

これをコンパイルします。

```
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
