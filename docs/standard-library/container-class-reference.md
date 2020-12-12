---
description: '詳細については、コンテナークラス:: reference に関するページを参照してください。'
title: コンテナー クラス::reference
ms.date: 11/04/2016
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
ms.openlocfilehash: e3a143ec9a195f7ea42f3b067a72b40ef5be9283
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324842"
---
# <a name="container-classreference"></a>コンテナー クラス::reference

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

被制御シーケンスの要素への参照として使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
typedef T2 reference;
```

## <a name="remarks"></a>解説

ここでは、指定されていない型 `T2` (通常は) のシノニムとして記述されてい `Alloc::reference` ます。 型のオブジェクトは `reference` [const_reference](../standard-library/container-class-const-reference.md)型のオブジェクトにキャストできます。

## <a name="see-also"></a>関連項目

[サンプルコンテナークラス](../standard-library/sample-container-class.md)
