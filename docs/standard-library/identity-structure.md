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
ms.openlocfilehash: 62acade082847386e065470f23ffe8374f82eb55
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079195"
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
