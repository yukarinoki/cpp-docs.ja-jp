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
ms.openlocfilehash: 6d1b82e3f60428e3a778709dc69de983a7f886bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317671"
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
|[サイズ::Cサイズ](#csize)|`CSize` オブジェクトを構築します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cサイズ::演算子 -](#operator_-)|2 つのサイズを減算します。|
|[Cサイズ::演算子!=](#operator_neq)|サイズとの間`CSize`の不等値をチェックします。|
|[Cサイズ::演算子 +](#operator_add)|2 つのサイズを追加します。|
|[Cサイズ::演算子 +=](#operator_add_eq)|にサイズを追加`CSize`します。|
|[Cサイズ::演算子 -=](#operator_-_eq)|からサイズを減算`CSize`します。|
|[Cサイズ::演算子 ==](#operator_eq_eq)|サイズとの間`CSize`の等値をチェックします。|

## <a name="remarks"></a>解説

このクラスは、構造体から`SIZE`派生します。 つまり`CSize`、 を呼び出`SIZE`すパラメーターで、`SIZE`構造体のデータ メンバーが アクセス可能なデータ メンバーであることを`CSize`示します。

`cx`と`cy`の`SIZE`メンバーと`CSize`のメンバーは公開されています。 さらに、`CSize`構造体を操作するメンバー関数を実装`SIZE`します。

> [!NOTE]
> 共有ユーティリティ クラスの詳細については、「`CSize`[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`tagSIZE`

`CSize`

## <a name="requirements"></a>必要条件

**ヘッダー:** atltypes.h

## <a name="csizecsize"></a><a name="csize"></a>サイズ::Cサイズ

`CSize` オブジェクトを構築します。

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>パラメーター

*イニトCX*<br/>
の`cx`メンバーを設定します`CSize`。

*イニシティ*<br/>
の`cy`メンバーを設定します`CSize`。

*イニトサイズ*<br/>
[SIZE](/windows/win32/api/windef/ns-windef-size)の`CSize`構造体またはオブジェクトを`CSize`初期化するために使用します。

*イニトプト*<br/>
[初期化](/windows/win32/api/windef/ns-windef-point)に使用`CPoint`される POINT`CSize`構造体またはオブジェクト。

*Dwsize*<br/>
初期化に使用される`CSize`DWORD 下位ワードは`cx`メンバーで、上位ワードは`cy`メンバーです。

### <a name="remarks"></a>解説

引数が指定されていない場合`cx``cy`は、ゼロに初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a>Cサイズ::演算子 ==

2 つのサイズ間の等しいかどうかをチェックします。

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>解説

サイズが等しい場合は 0 以外を返し、0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a>Cサイズ::演算子!=

2 つのサイズの間の不等式をチェックします。

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>解説

サイズが等しくない場合は 0 以外を返し、それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a>Cサイズ::演算子 +=

この`CSize`サイズを追加します。

```
void operator+=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a>Cサイズ::演算子 -=

この`CSize`サイズからサイズを減算します。

```
void operator-=(SIZE size) throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a>Cサイズ::演算子 +

これらの演算子は、`CSize`パラメーターの値にこの値を追加します。

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>解説

個々の演算子の説明は次のとおりです。

- **演算子 +(***サイズ***)**

  この操作では、2 つの値が`CSize`追加されます。

- **演算子 +(***ポイント***)**

  この操作は、この`CSize`値によって[POINT](/previous-versions/dd162805\(v=vs.85\)) (または[CPoint)](../../atl-mfc-shared/reference/cpoint-class.md)の値をオフセット (移動) します。 この`cx``CSize`値`cy`の と のメンバーは、 `x` `y`値のデータ・`POINT`メンバーおよびデータ・メンバーに追加されます。 [これは、SIZE](/windows/win32/api/windef/ns-windef-size)パラメータを受け取る[CPoint::演算子 +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)のバージョンに似ています。

- **演算子 +(** *lpRect* **)**

   この操作は、RECT (または[CRect)](../../atl-mfc-shared/reference/crect-class.md)の値をこの`CSize`値でオフセット (移動) します。 [RECT](/previous-versions/dd162897\(v=vs.85\)) この`cx``CSize`値`cy`の および のメンバーは`left`、 `top`、 `right`、`bottom`および 値の`RECT`データ・メンバーに追加されます。 [これは、SIZE](/windows/win32/api/windef/ns-windef-size)パラメータを受け取る[CRect::演算子 +](../../atl-mfc-shared/reference/crect-class.md#operator_add)のバージョンに似ています。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a>Cサイズ::演算子 -

これらの演算子のうち最初の 3`CSize`つの演算子は、この値をパラメータの値に減算します。

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>解説

4 番目の演算子である単項マイナスは、値の符号`CSize`を変更します。 個々の演算子の説明は次のとおりです。

- **演算子 -(** *サイズ* **)**

  この操作では、2`CSize`つの値が減算されます。

- **演算子 -(***ポイント***)**

  この操作は、この`CSize`値の加算反転によって[POINT](/previous-versions/dd162805\(v=vs.85\))または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)値をオフセット (移動) します。 この`cx``CSize`値`cy`の と の 値は`x`、`y`値の データ`POINT`・メンバーおよびデータ・メンバーから減算されます。 [これは、SIZE](/windows/win32/api/windef/ns-windef-size)パラメータを受け取る[CPoint::演算子](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)のバージョンに似ています。

- 演算子 *-(lpRect)* **)** **operator -(**

  この操作は、この`CSize`値の加算反転によって RECT または[CRect](../../atl-mfc-shared/reference/crect-class.md)値をオフセット (移動) します。 [RECT](/previous-versions/dd162897\(v=vs.85\)) この`cx``CSize`値`cy`の および のメンバーは、 `left`、 `top` `right`、および`bottom`値のデータ`RECT`・メンバーから減算されます。 [これは、SIZE](/windows/win32/api/windef/ns-windef-size)パラメータを受け取る[CRect::演算子](../../atl-mfc-shared/reference/crect-class.md#operator_-)のバージョンに似ています。

- **演算子 -()**

  この操作は、この`CSize`値の加算逆を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint クラス](../../atl-mfc-shared/reference/cpoint-class.md)
