---
title: コンテナー クラス::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: b344747c42e9b8b751b97747aacec0b39d10d6a1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221516"
---
# <a name="container-classswap"></a>コンテナー クラス::swap

> [!NOTE]
> このトピックでは、Microsoft では、C++ドキュメントで使用されるコンテナーの機能の例として、C++標準ライブラリ。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

**\*this** とその引数の間で被制御シーケンスを交換します。

## <a name="syntax"></a>構文

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Remarks

**\*this.get\_allocator ==** _right_**.get_allocator** の場合、一定時間で交換します。 それ以外の場合、2 つの被制御シーケンス内の要素数に比例した回数、要素の割り当てとコンストラクター呼び出しが実行されます。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
