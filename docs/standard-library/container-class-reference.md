---
title: コンテナー クラス::reference
ms.date: 11/04/2016
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
ms.openlocfilehash: ccd944e433e332ddd75f8a26e8db919c26d6e35b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453314"
---
# <a name="container-classreference"></a>コンテナー クラス::reference

> [!NOTE]
> このトピックは、 C++ C++標準ライブラリで使用されているコンテナーの非機能例として、Microsoft ドキュメントに記載されています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

被制御シーケンスの要素への参照として使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```

typedef T2 reference;
```

## <a name="remarks"></a>Remarks

ここでは、指定されていない型`T2` (通常`Alloc::reference`は) のシノニムとして記述されています。 型`reference`のオブジェクトは、 [const_reference](../standard-library/container-class-const-reference.md)型のオブジェクトにキャストできます。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)
