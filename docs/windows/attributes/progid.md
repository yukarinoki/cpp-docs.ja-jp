---
title: progid (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 136c651ec92c78339c2f701804a6a409523dd30f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839999"
---
# <a name="progid"></a>progid

COM オブジェクトの ProgID を指定します。

## <a name="syntax"></a>構文

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>パラメーター

*name*<br/>
オブジェクトを表す ProgID。

Progid には、COM/ActiveX オブジェクトを識別するために使用されるクラス識別子 (CLSID) のユーザーが判読できるバージョンが存在します。

## <a name="remarks"></a>解説

`progid`C++ 属性を使用すると、COM オブジェクトの ProgID を指定できます。 ProgID は、name1. *name2.* という形式になります。 ProgID の *バージョン* を指定しない場合、既定のバージョンは1になります。 *Name1*を指定しない場合、既定の名前は*classname. classname*になります。 を指定せずにを指定した場合 `progid` `vi_progid` 、 *name1* はから取得され、 `vi_progid` (次の連続番号) バージョンが追加されます。

を使用する属性ブロックで `progid` もが使用されていない場合、コンパイラはレジストリを調べて、指定されたのが `uuid` 存在するかどうかを確認します `uuid` `progid` 。 `progid`が指定されていない場合は、バージョン (コクラスを作成する場合は、コクラスの名前) がを生成するために使用され `progid` ます。

`progid` は属性を意味し `coclass` ます。つまり、を指定する場合は、属性 `progid` と属性を指定することと同じです `coclass` `progid` 。

`progid`属性により、指定した名前でクラスが自動的に登録されます。 生成された .idl ファイルには値が表示されません `progid` 。

ATL を使用するプロジェクト内でこの属性を使用すると、属性の動作が変更されます。 上記の動作に加えて、この属性で指定された情報は、 `GetProgID` 属性によって挿入される関数で使用され `coclass` ます。 詳細については、「 [coclass](coclass.md) 属性」を参照してください。

## <a name="example"></a>例

の使用例については、「 [コクラス](coclass.md) 」の例を参照してください `progid` 。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|`class`, `struct`|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID キー](/windows/win32/com/-progid--key)
