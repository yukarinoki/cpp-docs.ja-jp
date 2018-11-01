---
title: エントリ (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: b6c34a603f3ba8abaf070759a22ddf2b8e9c2106
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663256"
---
# <a name="entry"></a>entry

DLL 内のエントリ ポイントを識別することによって、モジュールで、エクスポートされた関数または定数を指定します。

## <a name="syntax"></a>構文

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
エントリ ポイントの ID。

## <a name="remarks"></a>Remarks

**エントリ**C++ 属性と同じ機能を持つ、[エントリ](/windows/desktop/Midl/entry)MIDL 属性。

## <a name="example"></a>例

例をご覧ください[idl_module](idl-module.md)の使用例の**エントリ**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|`idl_module` 属性|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)