---
title: vi_progid (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: b27a9a2f5a05535bd11b8091059e5be277b9692c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832920"
---
# <a name="vi_progid"></a>vi_progid

バージョンに依存しない ProgID の形式を指定します。

## <a name="syntax"></a>構文

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>パラメーター

*name*<br/>
オブジェクトを表すバージョンに依存しない ProgID。

Progid には、COM/ActiveX オブジェクトを識別するために使用されるクラス識別子 (CLSID) のユーザーが判読できるバージョンが存在します。

## <a name="remarks"></a>解説

**Vi_progid** C++ 属性を使用すると、COM オブジェクトのバージョンに依存しない progid を指定できます。 ProgID は、name1. *name2.* という形式になります。 バージョンに依存しない ProgID には *バージョン*がありません。 では、と vi_progid の両方の属性を指定でき `progid` **vi_progid** `coclass` ます。 **Vi_progid**を指定しない場合、バージョンに依存しない progid が[progid](progid.md)属性によって指定された値になります。

**vi_progid** は属性を意味し `coclass` ます。つまり、 **vi_progid**を指定した場合は、 `coclass` 属性と **vi_progid** 属性を指定することと同じです。

**Vi_progid**属性を指定すると、指定した名前でクラスが自動的に登録されます。 生成された .idl ファイルには ProgID 値が表示されません。

ATL プロジェクトでは、 [coclass](coclass.md) 属性も存在する場合、指定した ProgID が関数によって使用され `GetVersionIndependentProgID` ます (属性によって挿入され `coclass` ます)。

## <a name="example"></a>例

**Vi_progid**の使用例については、[コクラス](coclass.md)の例を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[ProgID キー](/windows/win32/com/-progid--key)
