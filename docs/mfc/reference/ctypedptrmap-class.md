---
title: CTypedPtrMap クラス
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 410f0101fd0f8cda271fe0f2353b06b9e8d773b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754364"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap クラス

ポインター マップ クラス `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`、および `CMapStringToPtr`のオブジェクトに対してタイプ セーフな "ラップ" が用意されています。

## <a name="syntax"></a>構文

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
型指定されたポインター マップ クラスの基本クラス。ポインター マップ クラス 、 `CMapPtrToPtr` `CMapPtrToWord`、 `CMapWordToPtr`、`CMapStringToPtr`または を指定する必要があります。

*キー*<br/>
マップのキーとして使用されるオブジェクトのクラス。

*値*<br/>
マップに格納されているオブジェクトのクラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クタイプタイプのマップ::ゲット・ネクスト・アソック](#getnextassoc)|反復処理の次の要素を取得します。|
|[クタイプ付きプサーマップ::ルックアップ](#lookup)|を基`KEY`にしてを`VALUE`返します。|
|[キーの削除](#removekey)|キーで指定された要素を削除します。|
|[クタイププターマップ::セットアット](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[クタイププターマップ::演算子\[\]](#operator_at)|マップに要素を挿入します。|

## <a name="remarks"></a>解説

を使用`CTypedPtrMap`すると、C++ 型検査機能を使用すると、ポインター型の不一致によって発生するエラーを排除できます。

すべての`CTypedPtrMap`関数がインラインであるため、このテンプレートを使用しても、コードのサイズや速度に大きな影響はありません。

の使用方法`CTypedPtrMap`の詳細については、「 コレクションと[テンプレート ベースのクラス](../../mfc/template-based-classes.md)」を参照してください。 [Collections](../../mfc/collections.md)

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>クタイプタイプのマップ::ゲット・ネクスト・アソック

で`rNextPosition`マップ要素を取得し、マップ内`rNextPosition`の次の要素を参照するように更新します。

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*r位置*<br/>
前`GetNextAssoc``BASE_CLASS`または **::GetStartPosition**呼び出しによって返される POSITION 値への参照を指定します。

*キー*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*rキー*<br/>
取得した要素の返されたキーを指定します。

*値*<br/>
マップの値の型を指定するテンプレート パラメーター。

*Rvalue*<br/>
取得した要素の戻り値を指定します。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も便利です。 位置順序は、必ずしもキー値シーケンスと同じではありません。

取得された要素がマップ内の最後の要素である場合、新しい値`rNextPosition`は NULL に設定されます。

このインライン関数は`BASE_CLASS`**::GetNextAssoc**を呼び出します。

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a>クタイプ付きプサーマップ::ルックアップ

`Lookup`ハッシュ アルゴリズムを使用して、正確に一致するキーを持つ map 要素をすばやく見つけることができます。

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
このマップのクラスの基本クラスを指定するテンプレート パラメーター。

*key*<br/>
検索する要素のキー。

*値*<br/>
このマップに格納されている値の種類を指定するテンプレート パラメーター。

*Rvalue*<br/>
取得した要素の戻り値を指定します。

### <a name="return-value"></a>戻り値

要素が見つかった場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このインライン関数は`BASE_CLASS`**、::Lookup**を呼び出します。

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrマップ::演算子 [ ]

この演算子は、代入ステートメントの左側 (左辺値) でのみ使用できます。

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>パラメーター

*値*<br/>
このマップに格納されている値の種類を指定するテンプレート パラメーター。

*BASE_CLASS*<br/>
このマップのクラスの基本クラスを指定するテンプレート パラメーター。

*key*<br/>
マップ内で検索または作成する要素のキー。

### <a name="remarks"></a>解説

指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。 マップ内にキーが見つからない可能性があるため、この演算子と同等の"右辺"(r値)はありません。 要素を`Lookup`取得するには、メンバー関数を使用します。

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a>キーの削除

このメンバー関数は`BASE_CLASS`**、::RemoveKey**を呼び出します。

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>パラメーター

*キー*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*key*<br/>
削除する要素のキー。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

詳細な説明については[、「CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)」を参照してください。

## <a name="ctypedptrmapsetat"></a><a name="setat"></a>クタイププターマップ::セットアット

このメンバー関数は`BASE_CLASS`**、::SetAt**を呼び出します。

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>パラメーター

*キー*<br/>
マップのキーの種類を指定するテンプレート パラメーター。

*key*<br/>
newValue のキー値を指定します。

*newValue*<br/>
新しい要素の値であるオブジェクト ポインターを指定します。

### <a name="remarks"></a>解説

詳細な説明については[、「CMapStringToOb::SetAt」](../../mfc/reference/cmapstringtoob-class.md#setat)を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル コレクト](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)<br/>
[クラスを使用します。](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[クラスを作成します。](../../mfc/reference/cmapstringtoptr-class.md)
