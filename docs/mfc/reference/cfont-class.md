---
title: CFont クラス
ms.date: 11/04/2016
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
ms.openlocfilehash: c37b2f657105e0065e0cddb2c508424bd6c89b0a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424393"
---
# <a name="cfont-class"></a>CFont クラス

Windows のグラフィック デバイス インターフェイス (GDI) のフォントをカプセル化したもので、フォントを操作するメンバー関数を提供します。

## <a name="syntax"></a>構文

```
class CFont : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CFont:: CFont](#cfont)|`CFont` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CFont:: CreateFont](#createfont)|指定した特性を使用して `CFont` を初期化します。|
|[CFont:: CreateFontIndirect](#createfontindirect)|`LOGFONT` 構造体で指定された特性を使用して `CFont` オブジェクトを初期化します。|
|[CFont:: CreatePointFont](#createpointfont)|指定した高さを使用して、1秒単位で測定した `CFont` を初期化します。|
|[CFont:: CreatePointFontIndirect](#createpointfontindirect)|`CreateFontIndirect` と同じですが、フォントの高さは論理単位ではなく、1/10 ポイントで測定される点が異なります。|
|[CFont:: FromHandle](#fromhandle)|Windows HFONT が指定されている場合に、`CFont` オブジェクトへのポインターを返します。|
|[CFont:: GetLogFont](#getlogfont)|`LOGFONT` に、`CFont` オブジェクトにアタッチされている論理フォントに関する情報を格納します。|

### <a name="public-operators"></a>パブリック演算子

|Name|Description|
|----------|-----------------|
|[CFont:: operator HFONT](#operator_hfont)|`CFont` オブジェクトにアタッチされている Windows GDI フォントハンドルを返します。|

## <a name="remarks"></a>解説

`CFont` オブジェクトを使用するには、`CFont` オブジェクトを構築し、 [Createfont](#createfont)、 [createfontindirect](#createfontindirect)、 [createpointfont](#createpointfont)、または[Createpointfontindirect](#createpointfontindirect)を使用して Windows フォントをそのオブジェクトに添付し、オブジェクトのメンバー関数を使用してフォントを操作します。

`CreatePointFont` 関数と `CreatePointFontIndirect` 関数は、ポイントサイズから論理単位に自動的にフォントの高さを変換するため、`CreateFont` または `CreateFontIndirect` よりも簡単に使用できます。

`CFont`の詳細については、「[グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cfont"></a>CFont:: CFont

`CFont` オブジェクトを構築します。

```
CFont();
```

### <a name="remarks"></a>解説

結果として得られるオブジェクトは、使用する前に、`CreateFont`、`CreateFontIndirect`、`CreatePointFont`、または `CreatePointFontIndirect` で初期化する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

##  <a name="createfont"></a>CFont:: CreateFont

指定した特性を使用して `CFont` オブジェクトを初期化します。

```
BOOL CreateFont(
    int nHeight,
    int nWidth,
    int nEscapement,
    int nOrientation,
    int nWeight,
    BYTE bItalic,
    BYTE bUnderline,
    BYTE cStrikeOut,
    BYTE nCharSet,
    BYTE nOutPrecision,
    BYTE nClipPrecision,
    BYTE nQuality,
    BYTE nPitchAndFamily,
    LPCTSTR lpszFacename);
```

### <a name="parameters"></a>パラメーター

*nHeight*<br/>
フォントの必要な高さ (論理単位) を指定します。 説明については、Windows SDK の[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体の `lfHeight` メンバーを参照してください。 *NHeight*の絶対値は、変換後に16384デバイスユニットを超えることはできません。 すべての高さの比較で、フォントマッパーは、要求されたサイズを超えない最大のフォント、またはすべてのフォントが要求されたサイズを超えた場合に最小のフォントを検索します。

*nWidth*<br/>
フォントの文字の平均幅 (論理単位) を指定します。 *NWidth*が0の場合、デバイスの縦横比が、使用可能なフォントのデジタル化された縦横比と照合され、最も近い一致が検索されます。これは、差分の絶対値によって決まります。

*nEscapement*<br/>
傾斜ベクターとディスプレイサーフェイスの x 軸の間の角度 (0.1 度単位) を指定します。 傾斜ベクターは、行の最初と最後の文字の原点を通る線です。 角度は、x 軸から反時計回りに計測されます。 詳細については、Windows SDK の `LOGFONT` 構造体の `lfEscapement` メンバーを参照してください。

*nOrientation*<br/>
文字のベースラインと x 軸の間の角度 (0.1 度単位) を指定します。 角度は、y 方向が上にある座標系の y 方向が下向きで x 軸から時計回りになる座標系の x 軸から反時計回りに計測されます。

*nWeight*<br/>
フォントの太さ (1000 あたりインク付きピクセル単位) を指定します。 詳細については、Windows SDK の `LOGFONT` 構造体にある*lfWeight*メンバーを参照してください。 説明されている値は概数です。実際の外観は、タイプフェイスによって異なります。 一部のフォントには、FW_NORMAL、FW_REGULAR、および FW_BOLD の重みしかありません。 FW_DONTCARE が指定されている場合は、既定の重みが使用されます。

*bItalic*<br/>
フォントを斜体にするかどうかを指定します。

*bUnderline*<br/>
フォントを下線付きにするかどうかを指定します。

*cStrikeOut*<br/>
フォントの文字を取り消してもよいかどうかを指定します。0以外の値に設定されている場合は、取り消し線のフォントを指定します。

*nCharSet*<br/>
フォントの文字セットを指定します。値の一覧については、Windows SDK の `LOGFONT` 構造体の `lfCharSet` メンバーを参照してください。

OEM 文字セットはシステムに依存します。

他の文字セットを含むフォントがシステムに存在する可能性があります。 文字セットが不明なフォントを使用するアプリケーションでは、そのフォントで表示される文字列の変換または解釈を試行しないでください。 代わりに、文字列を出力デバイスドライバーに直接渡す必要があります。

フォントマッパーでは、DEFAULT_CHARSET 値は使用されません。 アプリケーションでこの値を使用して、フォントの名前とサイズが論理フォントを完全に記述できるようにすることができます。 指定した名前のフォントが存在しない場合は、任意の文字セットのフォントを指定したフォントに置き換えることができます。 予期しない結果を避けるために、アプリケーションでは DEFAULT_CHARSET 値を控えめに使用する必要があります。

*nOutPrecision*<br/>
目的の出力精度を指定します。 出力の有効桁数は、要求されたフォントの高さ、幅、文字の方向、傾斜、およびピッチ、出力がどの程度一致しなければならないか定義します。 値の一覧と詳細については、Windows SDK の `LOGFONT` 構造体の `lfOutPrecision` メンバーを参照してください。

*nClipPrecision*<br/>
目的のクリッピング精度を指定します。 クリッピング精度は、クリッピング領域の外側にある文字をクリップする方法を定義します。 値の一覧については、Windows SDK の `LOGFONT` 構造の `lfClipPrecision` メンバーを参照してください。

埋め込み読み取り専用フォントを使用するには、アプリケーションで CLIP_ENCAPSULATE を指定する必要があります。

デバイス、TrueType、ベクターフォントの一貫したローテーションを実現するために、アプリケーションでは、または演算子を使用して、CLIP_LH_ANGLES 値と他の任意の*nClipPrecision*値を組み合わせることができます。 CLIP_LH_ANGLES ビットが設定されている場合、すべてのフォントの回転は、座標系の向きが左ききか右ききかによって異なります。 (座標系の向きの詳細については、 *Norientation*パラメーターの説明を参照してください)。CLIP_LH_ANGLES が設定されていない場合、デバイスフォントは常に反時計回りに回転しますが、他のフォントの回転は座標系の向きに依存します。

*nQuality*<br/>
フォントの出力品質を指定します。これにより、GDI が論理フォント属性を実際の物理フォントの属性と一致させるために必要な方法が定義されます。 値の一覧については、Windows SDK の `LOGFONT` 構造の `lfQuality` メンバーを参照してください。

*nPitchAndFamily*<br/>
フォントのピッチとファミリを指定します。 値の一覧と詳細については、Windows SDK の `LOGFONT` 構造体の `lfPitchAndFamily` メンバーを参照してください。

*lpszFacename*<br/>
フォントのタイプフェイス名を指定する null で終わる文字列への `CString` またはポインター。 この文字列の長さは30文字以下でなければなりません。 Windows [Enumfontfamilies](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw)関数を使用すると、現在使用可能なすべてのフォントを列挙できます。 *Lpszfacename*が NULL の場合、GDI はデバイスに依存しないタイプフェイスを使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、その後、任意のデバイスコンテキストのフォントとして選択できます。

`CreateFont` 関数は、新しい Windows GDI フォントを作成しません。 GDI で使用可能な物理フォントから最も近い一致を選択するだけです。

アプリケーションでは、論理フォントを作成するときにほとんどのパラメーターに既定の設定を使用できます。 常に特定の値を指定する必要があるパラメーターは、 *nHeight*と*lpszfacename*です。 *NHeight*と*lpszfacename*がアプリケーションによって設定されていない場合、作成される論理フォントはデバイスに依存します。

`CreateFont` 関数によって作成された `CFont` オブジェクトを終了したら、`CDC::SelectObject` を使用してデバイスコンテキストに別のフォントを選択し、不要になった `CFont` オブジェクトを削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

##  <a name="createfontindirect"></a>CFont:: CreateFontIndirect

[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体で指定された特性を使用して `CFont` オブジェクトを初期化します。

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>パラメーター

*lpLogFont*<br/>
論理フォントの特性を定義する `LOGFONT` 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、その後、任意のデバイスの現在のフォントとして選択できます。

このフォントには、 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体で指定されている特性があります。 [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject)メンバー関数を使用してフォントを選択すると、GDI フォントマッパーは論理フォントと既存の物理フォントを一致させようとします。 フォントマッパーが論理フォントと完全に一致するものを見つけることができない場合は、要求された特性の多くを可能な限り満たす代替フォントが提供されます。

`CreateFontIndirect` 関数によって作成された `CFont` オブジェクトが不要になったら、`CDC::SelectObject` を使用してデバイスコンテキストに別のフォントを選択し、不要になった `CFont` オブジェクトを削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

##  <a name="createpointfont"></a>CFont:: CreatePointFont

この関数は、指定されたタイプフェイスとポイントサイズのフォントを簡単に作成する方法を提供します。

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>パラメーター

*nPointSize*<br/>
要求されたフォントの高さ (1/10 ポイント単位)。 (たとえば、12ポイントのフォントを要求するには、120を渡します)。

*lpszFaceName*<br/>
フォントのタイプフェイス名を指定する null で終わる文字列への `CString` またはポインター。 この文字列の長さは30文字以下でなければなりません。 Windows の EnumFontFamilies 関数を使用すると、現在使用可能なすべてのフォントを列挙できます。 *Lpszfacename*が NULL の場合、GDI はデバイスに依存しないタイプフェイスを使用します。

*pDC*<br/>
*NPointSize*の高さを論理単位に変換するために使用される[CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 NULL の場合、変換には画面デバイスコンテキストが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

*PDC*によってポイントされている CDC オブジェクトを使用して、 *nPointSize*の高さを論理単位に自動的に変換します。

`CreatePointFont` 関数によって作成された `CFont` オブジェクトの使用が終了したら、まずデバイスコンテキストからフォントを選択し、次に `CFont` オブジェクトを削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

##  <a name="createpointfontindirect"></a>CFont:: CreatePointFontIndirect

この関数は[Createfontindirect](#createfontindirect)と同じですが、`LOGFONT` の `lfHeight` メンバーは、デバイス単位ではなく、1/10 ポイントで解釈される点が異なります。

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>パラメーター

*lpLogFont*<br/>
論理フォントの特性を定義する[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体を指します。 `LOGFONT` 構造体の `lfHeight` メンバーは、論理単位ではなく、1/10 ポイントで測定されます。 (たとえば、12ポイントのフォントを要求するには、`lfHeight` を120に設定します)。

*pDC*<br/>
`lfHeight` の高さを論理単位に変換するために使用される[CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 NULL の場合、変換には画面デバイスコンテキストが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

この関数は、`LOGFONT` 構造体を Windows に渡す前に、 *pDC*が指す CDC オブジェクトを使用して、`lfHeight` の高さを論理単位に自動的に変換します。

`CreatePointFontIndirect` 関数によって作成された `CFont` オブジェクトの使用が終了したら、まずデバイスコンテキストからフォントを選択し、次に `CFont` オブジェクトを削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

##  <a name="fromhandle"></a>CFont:: FromHandle

Windows GDI フォントオブジェクトへの HFONT ハンドルが指定されている場合に、`CFont` オブジェクトへのポインターを返します。

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>パラメーター

*hFont*<br/>
Windows フォントを扱う HFONT ハンドル。

### <a name="return-value"></a>戻り値

成功した場合は `CFont` オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CFont` オブジェクトがハンドルにまだアタッチされていない場合は、一時 `CFont` オブジェクトが作成され、アタッチされます。 この一時 `CFont` オブジェクトは、アプリケーションが次にそのイベントループ内でアイドル状態になったときにのみ有効です。その時点で、すべての一時グラフィックオブジェクトが削除されます。 これを言うもう1つの方法は、一時オブジェクトが、1つのウィンドウメッセージの処理中にのみ有効であることです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

##  <a name="getlogfont"></a>CFont:: GetLogFont

`CFont`の `LOGFONT` 構造体のコピーを取得するには、この関数を呼び出します。

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>パラメーター

*pLogFont*<br/>
フォント情報を受け取る[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外。それ以外の場合は0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

##  <a name="operator_hfont"></a>CFont:: operator HFONT

この演算子を使用して、`CFont` オブジェクトにアタッチされているフォントの Windows GDI ハンドルを取得します。

```
operator HFONT() const;
```

### <a name="return-value"></a>戻り値

成功した場合に `CFont` にアタッチされた Windows GDI フォントオブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は `CFont` から[フォントおよびテキスト](/windows/win32/gdi/fonts-and-text)への変換に自動的に使用されるため、`CFont` オブジェクトを hfonts を想定している関数に渡すことができます。

グラフィックオブジェクトの使用方法の詳細については、「Windows SDK の[グラフィックオブジェクト](/windows/win32/gdi/graphic-objects)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>参照

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
