---
title: '&lt;new&gt; typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 5ab0087a85cb2fce6fa300db136e7c60c66b0b5c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852192"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

||
|-|
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

新しいハンドラーとして使用するのに適した関数を指す型。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>コメント

このハンドラー関数の型は、追加の記憶域の要求を満たすことができない場合に、**operatornew** または `operator new[]` によって呼び出されます。

### <a name="example"></a>例

`new_handler` を戻り値として使用する例については、「[set_new_handler](../standard-library/new-functions.md#set_new_handler)」をご覧ください。

## <a name="see-also"></a>関連項目

[\<new>](../standard-library/new.md)<br/>
