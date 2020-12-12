---
description: '詳細情報: Windows:: Foundation:: Collections 名前空間 (C++/CX)'
title: Windows::Foundation::Collections 名前空間 (C++/CX)
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections
helpviewer_keywords:
- Windows::Foundation::Collections Namespace (C++/CX)
ms.assetid: 04bd3543-e30f-4fd2-95ee-272a3fcd0158
ms.openlocfilehash: 74086268215c83f1cf4bd9bca8b60923bfcc6725
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288010"
---
# <a name="windowsfoundationcollections-namespace-ccx"></a>Windows::Foundation::Collections 名前空間 (C++/CX)

C++/CX は、Vector、VectorView、Map、および MapView コレクションクラスの使用を簡略化する関数を使用して、Windows:: Foundation:: Collections 名前空間を補完します。

## <a name="syntax"></a>構文

```

namespace Windows {
    namespace Foundation {
        namespace Collections;
    }
}
```

### <a name="functions"></a>関数

|名前|説明|
|----------|-----------------|
|[back_inserter 関数](../cppcx/back-inserter-function.md)|コレクションの末尾に値を挿入するために使用できる反復子を返します。|
|[begin 関数](../cppcx/begin-function.md)|コレクションの先頭を指す反復子を返します。|
|[end 関数](../cppcx/end-function.md)|コレクションの末尾を越えて指す反復子を返します。|
|[to_vector 関数](../cppcx/to-vector-function.md)|コレクションを std::vector として返します。|

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Windows::Foundation::Collections
