---
title: コンテナー クラス::reference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cad92eb5ce664d22cc5ee0ad8b4c26d41c88d883
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="container-classreference"></a>コンテナー クラス::reference

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

被制御シーケンスの要素への参照として使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```

typedef T2 reference;
```

## <a name="remarks"></a>コメント

ここでは、指定されていない型 **T2** のシノニムとして記述されています (通常は **Alloc::reference**)。 **reference** 型のオブジェクトは、[const_reference](../standard-library/container-class-const-reference.md) 型のオブジェクトにキャストできます。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
