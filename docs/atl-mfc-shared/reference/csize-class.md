---
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
ms.openlocfilehash: 5e19ab9b9339f3e6f61abf7731a40ed3832b50c9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767363"
---
# <a name="csize-class"></a>CSize クラス

Windows の [SIZE](/windows/desktop/api/windef/ns-windef-tagsize) 構造体と同様に、相対座標や位置を実装します。

## <a name="syntax"></a>構文

```
class CSize : public tagSIZE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSize::CSize](#csize)|`CSize` オブジェクトを構築します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSize::operator-](#operator_-)|2 つのサイズを減算します。|
|[CSize::operator! =](#operator_neq)|間の不等性を確認します`CSize`とサイズ。|
|[CSize::operator +](#operator_add)|2 つのサイズを追加します。|
|[CSize::operator + =](#operator_add_eq)|サイズを追加します`CSize`します。|
|[CSize::operator =](#operator_-_eq)|サイズを減算`CSize`します。|
|[CSize::operator ==](#operator_eq_eq)|等しいかどうかを確認します`CSize`とサイズ。|

## <a name="remarks"></a>Remarks

このクラスから派生、`SIZE`構造体。 つまり、渡すことができます、`CSize`を呼び出して取得するパラメーターで、`SIZE`とのデータ メンバー、`SIZE`構造体のアクセス可能なデータ メンバーである`CSize`します。

`cx`と`cy`のメンバー `SIZE` (と`CSize`) は public です。 さらに、`CSize`を操作するメンバー関数の実装、`SIZE`構造体。

> [!NOTE]
> 詳細については、共有ユーティリティ クラス (など`CSize`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`tagSIZE`

`CSize`

## <a name="requirements"></a>必要条件

**ヘッダー:** atltypes.h

##  <a name="csize"></a>  CSize::CSize

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
セット、`cx`のメンバー、`CSize`します。

*initCY*<br/>
セット、`cy`のメンバー、`CSize`します。

*initSize*<br/>
[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)構造または`CSize`オブジェクトの初期化に使用される`CSize`します。

*initPt*<br/>
[ポイント](/windows/desktop/api/windef/ns-windef-tagpoint)構造または`CPoint`オブジェクトの初期化に使用される`CSize`します。

*dwSize*<br/>
DWORD が初期化に使用される`CSize`します。 下位ワードは、`cx`メンバーと、上位の単語は、`cy`メンバー。

### <a name="remarks"></a>Remarks

引数を指定しない場合`cx`と`cy`ゼロに初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

##  <a name="operator_eq_eq"></a>  CSize::operator ==

2 つのサイズに等しいかどうかを確認します。

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Remarks

0 は、サイズが等しい場合は 0 以外を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

##  <a name="operator_neq"></a>  CSize::operator! =

2 つのサイズ間の不等性を確認します。

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Remarks

サイズが等しくない場合、0 以外の値を返しますそれ以外の場合に 0 です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

##  <a name="operator_add_eq"></a>  CSize::operator + =

このサイズを追加します。`CSize`します。

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

##  <a name="operator_-_eq"></a>  CSize::operator =

これからサイズを減算`CSize`します。

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

##  <a name="operator_add"></a>  CSize::operator +

これらの演算子は、これを追加`CSize`値パラメーターの値にします。

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Remarks

次の各演算子の説明を参照してください。

- **operator +(** *size* **)**

  この操作では、2 つ追加します`CSize`値。

- **operator +(** *point* **)**

  この操作のオフセット (移動)、[ポイント](/previous-versions/dd162805\(v=vs.85\))(または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) この値`CSize`値。 `cx`と`cy`this のメンバー`CSize`に値を追加、`x`と`y`のデータ メンバー、`POINT`値。 バージョンと似ています[CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)を受け取る、[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)パラメーター。

- **operator +(** *lpRect* **)**

   この操作のオフセット (移動)、 [RECT](/previous-versions/dd162897\(v=vs.85\)) (または[CRect](../../atl-mfc-shared/reference/crect-class.md)) この値`CSize`値。 `cx`と`cy`this のメンバー`CSize`に値を追加、 `left`、 `top`、 `right`、および`bottom`のデータ メンバー、`RECT`値。 バージョンと似ています[CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add)を受け取る、[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)パラメーター。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

##  <a name="operator_-"></a>  CSize::operator -

この最初の 3 つの演算子が減算`CSize`値パラメーターの値にします。

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Remarks

4 番目の演算子では、単項マイナス、変更の符号、`CSize`値。 次の各演算子の説明を参照してください。

- **演算子-(** *サイズ* **)**

  この操作では、2 つを減算`CSize`値。

- **演算子-(** *ポイント* **)**

  この操作のオフセット (移動)、[ポイント](/previous-versions/dd162805\(v=vs.85\))または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)これの加法逆元によって値`CSize`値。 `cx`と`cy`この`CSize`から値が減算されて、`x`と`y`のデータ メンバー、`POINT`値。 バージョンと似ています[CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)を受け取る、[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)パラメーター。

- **operator -(** *lpRect* **)**

  この操作のオフセット (移動)、 [RECT](/previous-versions/dd162897\(v=vs.85\))または[CRect](../../atl-mfc-shared/reference/crect-class.md)これの加法逆元によって値`CSize`値。 `cx`と`cy`this のメンバー`CSize`から値が減算されて、 `left`、 `top`、 `right`、および`bottom`のデータ メンバー、`RECT`値。 バージョンと似ています[CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-)を受け取る、[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)パラメーター。

- **operator -()**

  この操作はこれの加法逆元を返します`CSize`値。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint クラス](../../atl-mfc-shared/reference/cpoint-class.md)
