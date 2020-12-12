---
description: 詳細については、「コンパイラの警告 C4368」を参照してください。
title: コンパイラの警告 C4368
ms.date: 11/04/2016
f1_keywords:
- C4368
helpviewer_keywords:
- C4368
ms.assetid: cb85bcee-fd3d-4aa5-b626-2324f07a4f1b
ms.openlocfilehash: 106d8b0bb0dc70f03017892e8597c0cf059016cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180787"
---
# <a name="compiler-warning-c4368"></a>コンパイラの警告 C4368

'メンバー' をマネージド '型' のメンバーとして定義できません。混合型はサポートされていません

CLR 型にネイティブ データ メンバーを埋め込むことはできません。

ただし、ネイティブ型へのポインターを宣言し、その有効期間をマネージド クラスのコンストラクター、デストラクター、およびファイナライザーで制御することはできます。 詳細については [、「デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。

この警告は、常にエラーとして表示されます。 C4368 を無効にするには、 [warning](../../preprocessor/warning.md) プラグマを使用します。

## <a name="example"></a>例

次の例では、C4368 が生成されます。

```cpp
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
