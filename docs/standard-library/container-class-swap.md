---
description: '詳細については、コンテナークラス:: swap に関するページを参照してください。'
title: コンテナー クラス::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: a38dd6d14ada3ad50927060ccec1542ebf2fd4ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233358"
---
# <a name="container-classswap"></a>コンテナー クラス::swap

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

**\* この** とその引数の間で被制御シーケンスを交換します。

## <a name="syntax"></a>構文

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>解説

この場合、 **\* \_ アロケーター = =** _right_**.get_allocator** を取得すると、一定の時間だけスワップが実行されます。 それ以外の場合、2 つの被制御シーケンス内の要素数に比例した回数、要素の割り当てとコンストラクター呼び出しが実行されます。

## <a name="see-also"></a>関連項目

[サンプルコンテナークラス](../standard-library/sample-container-class.md)
