---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0fd249dd7591caaaf62a0b8a698085efedb1f25
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854536"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

`vector<bool>::reference` から `bool` への暗黙の変換を提供します。

## <a name="syntax"></a>構文

```cpp
operator bool() const;
```

## <a name="return-value"></a>戻り値

[vector\<bool>](../standard-library/vector-bool-class.md) オブジェクトの要素のブール値。

## <a name="remarks"></a>コメント

`vector<bool>` オブジェクトはこの演算子では変更できません。

## <a name="requirements"></a>要件

**ヘッダー:** \<vector>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ベクター\<bool >:: クラスを参照](../standard-library/vector-bool-reference-class.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
