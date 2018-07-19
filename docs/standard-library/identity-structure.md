---
title: identity 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f065f7c00d3853d00c1063cd5b2838ec6d1d27b4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38952998"
---
# <a name="identity-structure"></a>identity 構造体

テンプレート パラメーターの型定義を指定する構造体。

## <a name="syntax"></a>構文

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };
```
### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|指定する値。|

## <a name="remarks"></a>Remarks

このクラスにはパブリック型の定義 `type` が含まれています。これは、テンプレート パラメーターの型と同じです。 必要な型が関数パラメーターに設定されるようにするには、テンプレート関数 [forward](../standard-library/utility-functions.md#forward) と組み合わせて使用します。

以前のコードと互換性のため、クラスも定義 identity 関数`operator()`の引数を返す*左*します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<utility>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<utility>](../standard-library/utility.md)<br/>
