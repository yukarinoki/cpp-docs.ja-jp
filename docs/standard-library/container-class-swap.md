---
title: コンテナー クラス::swap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0ac2b3322f7f034c09c86f2307da2e3f3995c0d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842327"
---
# <a name="container-classswap"></a>コンテナー クラス::swap

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

**\*this** とその引数の間で被制御シーケンスを交換します。

## <a name="syntax"></a>構文

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>コメント

**\*this.get\_allocator ==** _right_**.get_allocator** の場合、一定時間で交換します。 それ以外の場合、2 つの被制御シーケンス内の要素数に比例した回数、要素の割り当てとコンストラクター呼び出しが実行されます。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
