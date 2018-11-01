---
title: コンパイラの警告 C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: b2af1166738d867c84ff4ebae832f831af7940ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485609"
---
# <a name="compiler-warning-c4368"></a>コンパイラの警告 C4368

'メンバー' をマネージド '型' のメンバーとして定義できません。混合型はサポートされていません

CLR 型にネイティブ データ メンバーを埋め込むことはできません。

ただし、ネイティブ型へのポインターを宣言し、その有効期間をマネージド クラスのコンストラクター、デストラクター、およびファイナライザーで制御することはできます。 詳細については、次を参照してください。[デストラクターおよびファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。

この警告は、常にエラーとして表示されます。 使用して、[警告](../../preprocessor/warning.md)プラグマ C4368 を無効にします。

## <a name="example"></a>例

次の例では、C4368 を生成します。

```
// C4368.cpp
// compile with: /clr /c
struct N {};
ref struct O {};
ref struct R {
    R() : m_p( new N ) {}
    ~R() { delete m_p; }

   property N prop;   // C4368
   int i[10];   // C4368

   property O ^ prop2;   // OK
   N * m_p;   // OK
};
```