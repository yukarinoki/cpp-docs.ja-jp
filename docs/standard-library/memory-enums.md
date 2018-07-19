---
title: '&lt;memory&gt; 列挙型 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 9b9ea485bb66292c3c0509036c22dd161a694dd3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961423"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 列挙型

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety 列挙型

`get_pointer_safety` によって返される可能性がある値の列挙型です。

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>Remarks

スコープを持つ**enum**によって返される値を定義します`get_pointer_safety()`:

`relaxed` -- 安全に派生していないポインター (明らかに、宣言されたオブジェクトまたは割り当てられたオブジェクトへのポインター) が、安全に派生したポインターと同じように扱われます。

`preferred` -- 上と同様ですが、安全に派生していないポインターを逆参照することはできません。

`strict` -- 安全に派生していないポインターは、安全に派生したポインターとは異なる方法で扱われる場合があります。

## <a name="see-also"></a>関連項目

[\<memory>](../standard-library/memory.md)<br/>
