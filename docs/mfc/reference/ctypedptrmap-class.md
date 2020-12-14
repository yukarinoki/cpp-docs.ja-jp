---
description: '詳細情報: CTypedPtrMap クラス'
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
ms.openlocfilehash: 25476a9195fe4a522ed31937dc1e2c5156ef6792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344992"
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
型指定されたポインターマップクラスの基本クラスです。ポインターマップクラス ( `CMapPtrToPtr` 、、 `CMapPtrToWord` `CMapWordToPtr` 、または) である必要があり `CMapStringToPtr` ます。

*KEY*<br/>
マップのキーとして使用されるオブジェクトのクラス。

*VALUE*<br/>
Map に格納されているオブジェクトのクラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTypedPtrMap:: GetNextAssoc](#getnextassoc)|反復処理の対象となる次の要素を取得します。|
|[CTypedPtrMap:: Lookup](#lookup)|`KEY`に基づいてを返し `VALUE` ます。|
|[CTypedPtrMap:: RemoveKey](#removekey)|キーによって指定された要素を削除します。|
|[CTypedPtrMap:: SetAt](#setat)|Map に要素を挿入します。一致するキーが見つかった場合は、既存の要素を置き換えます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTypedPtrMap:: operator \[\]](#operator_at)|Map に要素を挿入します。|

## <a name="remarks"></a>解説

を使用すると `CTypedPtrMap` 、C++ の型チェック機能によって、ポインター型の不一致によって発生するエラーを解消できます。

すべての `CTypedPtrMap` 関数がインラインであるため、このテンプレートを使用してもコードのサイズや速度に大きな影響はありません。

の使用方法の詳細については `CTypedPtrMap` 、「アーティクル [コレクション](../../mfc/collections.md) と [テンプレートベースのクラス](../../mfc/template-based-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>要件

**ヘッダー:** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a> CTypedPtrMap:: GetNextAssoc

で map 要素を取得 `rNextPosition` し、を更新し `rNextPosition` て、マップ内の次の要素を参照します。

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*rPosition*<br/>
Previous `GetNextAssoc` または `BASE_CLASS` **:: GetStartPosition** 呼び出しによって返される位置値への参照を指定します。

*KEY*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*rKey*<br/>
取得した要素の返されたキーを指定します。

*VALUE*<br/>
マップの値の型を指定するテンプレートパラメーター。

*右辺値*<br/>
取得した要素の戻り値を指定します。

### <a name="remarks"></a>解説

この関数は、マップ内のすべての要素を反復処理する場合に最も役立ちます。 位置シーケンスは必ずしもキー値のシーケンスと同じではないことに注意してください。

取得した要素が map 内の最後の要素である場合、の新しい値 `rNextPosition` は NULL に設定されます。

このインライン関数 `BASE_CLASS` **は、:: GetNextAssoc** を呼び出します。

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a> CTypedPtrMap:: Lookup

`Lookup` ハッシュアルゴリズムを使用して、正確に一致するキーを持つ map 要素をすばやく検索します。

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>パラメーター

*BASE_CLASS*<br/>
このマップのクラスの基本クラスを指定するテンプレートパラメーター。

*key*<br/>
検索する要素のキー。

*VALUE*<br/>
このマップに格納されている値の型を指定するテンプレートパラメーター。

*右辺値*<br/>
取得した要素の戻り値を指定します。

### <a name="return-value"></a>戻り値

要素が見つかった場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このインライン関数 `BASE_CLASS` **は、:: Lookup** を呼び出します。

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a> CTypedPtrMap:: operator []

この演算子は、代入ステートメント (左辺値) の左側でのみ使用できます。

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>パラメーター

*VALUE*<br/>
このマップに格納されている値の型を指定するテンプレートパラメーター。

*BASE_CLASS*<br/>
このマップのクラスの基本クラスを指定するテンプレートパラメーター。

*key*<br/>
マップで検索または作成する要素のキー。

### <a name="remarks"></a>解説

指定したキーを持つマップ要素がない場合は、新しい要素が作成されます。 マップ内にキーが見つからない可能性があるため、この演算子に相当する "右辺" (r 値) はありません。 `Lookup`要素の取得には、メンバー関数を使用します。

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a> CTypedPtrMap:: RemoveKey

このメンバー関数 `BASE_CLASS` **は、:: removekey** を呼び出します。

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>パラメーター

*KEY*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*key*<br/>
削除する要素のキー。

### <a name="return-value"></a>戻り値

エントリが見つかり、正常に削除された場合は0以外の値。それ以外の場合は0です。

### <a name="remarks"></a>解説

詳細については、「 [CMapStringToOb:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)」を参照してください。

## <a name="ctypedptrmapsetat"></a><a name="setat"></a> CTypedPtrMap:: SetAt

このメンバー関数 `BASE_CLASS` **は、:: SetAt** を呼び出します。

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>パラメーター

*KEY*<br/>
マップのキーの種類を指定するテンプレートパラメーター。

*key*<br/>
NewValue のキー値を指定します。

*newValue*<br/>
新しい要素の値であるオブジェクトポインターを指定します。

### <a name="remarks"></a>解説

詳細については、「 [CMapStringToOb:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル収集](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)
