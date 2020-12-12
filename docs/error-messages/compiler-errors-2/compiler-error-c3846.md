---
description: 詳細については、「コンパイラエラー C3846」を参照してください。
title: コンパイラ エラー C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 13c9cb7a9dde3710cac31d8ee79fb148f8ff67bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255393"
---
# <a name="compiler-error-c3846"></a>コンパイラ エラー C3846

' symbol ': ' assembly2 ' からシンボルをインポートできません: ' symbol ' は既に別のアセンブリ ' assembly1 ' からインポートされています

参照されたアセンブリからシンボルをインポートできませんでした。このシンボルは、参照アセンブリから既にインポートされています。

## <a name="example"></a>例

次の例では、C3846 が生成されます。

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

その後、次のようにコンパイルします。

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
