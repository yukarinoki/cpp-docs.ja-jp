---
title: retval (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 9f5ad86a289f8904278a58636e66809ae0edd55b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407407"
---
# <a name="retval"></a>retval

メンバーの戻り値を受け取るパラメーターを指定します。

## <a name="syntax"></a>構文

```cpp
[retval]
```

## <a name="remarks"></a>Remarks

**Retval** C++ 属性と同じ機能を持つ、 [retval](/windows/desktop/Midl/retval) MIDL 属性。

**retval**関数の宣言の最後の引数に表示する必要があります。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)の使用サンプル**retval**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|**out**|
|**無効な属性**|**in**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)