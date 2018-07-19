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
ms.openlocfilehash: 13883e1426be22c8cf3d329be33258c69511900d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966020"
---
# <a name="container-classreference"></a>コンテナー クラス::reference

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

被制御シーケンスの要素への参照として使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```

typedef T2 reference;
```

## <a name="remarks"></a>Remarks

説明されている、ここで指定されていない型のシノニムとして`T2`(通常`Alloc::reference`)。 型のオブジェクト`reference`型のオブジェクトにキャストできる[const_reference](../standard-library/container-class-const-reference.md)します。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
