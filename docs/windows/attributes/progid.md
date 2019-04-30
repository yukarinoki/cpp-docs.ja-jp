---
title: progid (C++ COM の属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 5b0c688ad4d9b607cc1f5fb6b1c6d536a1c7888e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407433"
---
# <a name="progid"></a>progid

COM オブジェクトの ProgID を指定します。

## <a name="syntax"></a>構文

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>パラメーター

*name*<br/>
オブジェクトを表す ProgID です。

Progid は、人間が判読できるバージョンの COM および ActiveX オブジェクトを識別するために使用したクラス id (CLSID) を提示します。

## <a name="remarks"></a>Remarks

**Progid** C++ 属性では、COM オブジェクトの ProgID を指定することができます。 ProgID がフォーム*name1.name2.version*します。 指定しない場合、*バージョン*ProgID の場合は、既定のバージョンは 1 です。 指定しない場合*name1.name2*、既定の名前は*classname.classname*します。 指定しない場合**progid**指定`vi_progid`、 *name1.name2*から取得されます`vi_progid`(次の連続番号) とバージョンが追加されます。

属性ブロックを使用する場合**progid**も使用しません**uuid**、コンパイラでチェックするかどうかをレジストリ、 **uuid** 、指定された存在**progid**. 場合**progid**が指定されていないバージョン (およびコクラスの名前、作成する場合) の生成に使用される、 **progid**します。

**progid**意味、`coclass`を指定する場合は、属性**progid**、指定した場合と同じことが、`coclass`と**progid**属性。

**Progid**属性によって指定された名前に自動的に登録するクラス。 生成された .idl ファイルが表示されない、 **progid**値。

この属性が ATL を使用するプロジェクト内で使用される場合、属性の動作を変更します。 上記の動作に加え、この属性で指定された情報がで使用される、`GetProgID`によって挿入関数、`coclass`属性。 詳細については、次を参照してください。、[コクラス](coclass.md)属性。

## <a name="example"></a>例

例をご覧ください[コクラス](coclass.md)の使用サンプル**progid**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID キー](/windows/desktop/com/-progid--key)
