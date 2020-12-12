---
description: '詳細: CSize クラス'
title: CSize クラス
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 0a63a7e0c48948406bf5650a1b095713f701a325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166643"
---
# <a name="csize-class"></a>CSize クラス

Windows の [SIZE](/windows/win32/api/windef/ns-windef-size) 構造体と同様に、相対座標や位置を実装します。

## <a name="syntax"></a>構文

```
class CSize : public tagSIZE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSize:: CSize](#csize)|`CSize` オブジェクトを構築します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSize:: operator-](#operator_-)|2つのサイズを減算します。|
|[CSize:: operator! =](#operator_neq)|とのサイズが等しくないかどうかを確認し `CSize` ます。|
|[CSize:: operator +](#operator_add)|2つのサイズを加算します。|
|[CSize:: operator + =](#operator_add_eq)|にサイズを追加し `CSize` ます。|
|[CSize:: operator-=](#operator_-_eq)|からサイズを減算 `CSize` します。|
|[CSize:: operator = =](#operator_eq_eq)|とのサイズが等しいかどうかをチェックし `CSize` ます。|

## <a name="remarks"></a>解説

このクラスは、 `SIZE` 構造体から派生します。 これは、を呼び出すパラメーターでを渡すことができ、 `CSize` `SIZE` 構造体のデータメンバー `SIZE` がのアクセス可能なデータメンバーであることを意味し `CSize` ます。

`cx` `cy` `SIZE` (および) のおよびメンバー `CSize` はパブリックです。 さらに、は、 `CSize` 構造体を操作するためのメンバー関数を実装し `SIZE` ます。

> [!NOTE]
> 共有ユーティリティクラス (など) の詳細につい `CSize` ては、「 [共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagSIZE`

`CSize`

## <a name="requirements"></a>要件

**ヘッダー:** atltypes. h

## <a name="csizecsize"></a><a name="csize"></a> CSize:: CSize

`CSize` オブジェクトを構築します。

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>パラメーター

*initCX*<br/>
のメンバーを設定 `cx` `CSize` します。

*initCY*<br/>
のメンバーを設定 `cy` `CSize` します。

*initSize*<br/>
初期化に使用する[サイズ](/windows/win32/api/windef/ns-windef-size)の構造体または `CSize` オブジェクト `CSize` 。

*initPt*<br/>
[](/windows/win32/api/windef/ns-windef-point)の `CPoint` 初期化に使用されるポイント構造またはオブジェクト `CSize` 。

*dwSize*<br/>
初期化に使用する DWORD `CSize` 。 下位ワードはメンバーであり、 `cx` 上位ワードは `cy` メンバーです。

### <a name="remarks"></a>解説

引数を指定しない場合、 `cx` および `cy` は0に初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a> CSize:: operator = =

2つのサイズが等しいかどうかをチェックします。

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>解説

サイズが等しい場合は0以外の値、otherwize は0を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a> CSize:: operator! =

2つのサイズが等しくないかどうかをチェックします。

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>解説

サイズが等しくない場合は0以外の値を返します。それ以外の場合は0を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a> CSize:: operator + =

サイズをこのに追加し `CSize` ます。

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a> CSize:: operator-=

このからサイズを減算 `CSize` します。

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a> CSize:: operator +

これら `CSize` の演算子は、この値をパラメーターの値に追加します。

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>解説

個々の演算子の次の説明を参照してください。

- **演算子 + (** *サイズ* **)**

  この操作では `CSize` 、2つの値を加算します。

- **演算子 + (** *point* **)**

  この操作では、この値によって [POINT](/windows/win32/api/windef/ns-windef-point) (または [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) 値がオフセット (移動) さ `CSize` れます。 `cx` `cy` この値のおよびメンバーは、 `CSize` `x` 値のおよびデータメンバーに追加され `y` `POINT` ます。 これは、 [SIZE](/windows/win32/api/windef/ns-windef-size)パラメーターを受け取る、 [CPoint:: operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)のバージョンに似ています。

- **演算子 + (** *lpRect* **)**

   この操作では、この値によって [RECT](/windows/win32/api/windef/ns-windef-rect) (または [CRect](../../atl-mfc-shared/reference/crect-class.md)) の値がオフセット (移動) さ `CSize` れます。 `cx` `cy` この値のおよびメンバーは、 `CSize` `left` 値の、、、およびの各データメンバーに追加され `top` `right` `bottom` `RECT` ます。 これは、[サイズ](/windows/win32/api/windef/ns-windef-size)パラメーターを受け取る、 [CRect:: operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add)のバージョンに似ています。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a> CSize:: operator-

これらの演算子の最初の3つは、この `CSize` 値をパラメーターの値に減算します。

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>解説

4番目の演算子 (単項マイナス) は、値の符号を変更し `CSize` ます。 個々の演算子の次の説明を参照してください。

- **operator-(** *サイズ* **)**

  この操作では `CSize` 、2つの値を減算します。

- **operator-(** *point* **)**

  この操作では、この値の加法逆によって、 [点](/windows/win32/api/windef/ns-windef-point) または [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 値がオフセット (移動) さ `CSize` れます。 `cx` `cy` この値のとは、 `CSize` `x` 値のおよびデータメンバーから減算され `y` `POINT` ます。 これは、 [SIZE](/windows/win32/api/windef/ns-windef-size)パラメーターを受け取る、 [CPoint:: operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)のバージョンに似ています。

- **operator-(** *lpRect* **)**

  この操作は、この値の加法逆によって [RECT](/windows/win32/api/windef/ns-windef-rect) または [CRect](../../atl-mfc-shared/reference/crect-class.md) の値をオフセット (移動) `CSize` します。 `cx` `cy` この値のおよびメンバーは、 `CSize` `left` 値の、、、およびの各データメンバーから減算され `top` `right` `bottom` `RECT` ます。 これは、[サイズ](/windows/win32/api/windef/ns-windef-size)パラメーターを受け取る、 [CRect:: operator](../../atl-mfc-shared/reference/crect-class.md#operator_-)のバージョンに似ています。

- **operator-()**

  この操作は、この値の加法逆を返し `CSize` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint クラス](../../atl-mfc-shared/reference/cpoint-class.md)
