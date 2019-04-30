---
title: '&lt;memory&gt; 列挙型'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 5c5f87905b772ef277a72ef11defef8cb1001661
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412840"
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
