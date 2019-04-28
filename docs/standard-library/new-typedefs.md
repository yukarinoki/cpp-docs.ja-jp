---
title: '&lt;new&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 85c8d0c2974f734783e3d9c2ad1269f84d605dec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223637"
---
# <a name="ltnewgt-typedefs"></a>&lt;new&gt; typedefs

| |
| - |
|[new_handler](#new_handler)|

## <a name="new_handler"></a>  new_handler

新しいハンドラーとして使用するのに適した関数を指す型。

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Remarks

このハンドラー関数の型は、追加の記憶域の要求を満たすことができない場合に、**operatornew** または `operator new[]` によって呼び出されます。

### <a name="example"></a>例

`new_handler` を戻り値として使用する例については、「[set_new_handler](../standard-library/new-functions.md#set_new_handler)」をご覧ください。

## <a name="see-also"></a>関連項目

[\<new>](../standard-library/new.md)<br/>
