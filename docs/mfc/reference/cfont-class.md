---
description: 詳細については、「CFont クラス」を参照してください。
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
ms.openlocfilehash: 4c3df138c80aeb572a4e449e7fe1065e70b5fe49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184414"
---
# <a name="cfont-class"></a>CFont クラス

Windows のグラフィック デバイス インターフェイス (GDI) のフォントをカプセル化したもので、フォントを操作するメンバー関数を提供します。

## <a name="syntax"></a>構文

```
class CFont : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFont:: CFont](#cfont)|`CFont` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFont:: CreateFont](#createfont)|指定した特性を使用して、を初期化し `CFont` ます。|
|[CFont:: CreateFontIndirect](#createfontindirect)|`CFont`構造体で指定された特性を使用してオブジェクトを初期化 `LOGFONT` します。|
|[CFont:: CreatePointFont](#createpointfont)|指定した高さを使用してを初期化し `CFont` ます。ポイントの1/10 として測定します。|
|[CFont:: CreatePointFontIndirect](#createpointfontindirect)|と同じですが `CreateFontIndirect` 、フォントの高さは論理単位ではなく1/10 ポイントで測定される点が異なります。|
|[CFont:: FromHandle](#fromhandle)|`CFont`Windows HFONT が指定されている場合に、オブジェクトへのポインターを返します。|
|[CFont:: GetLogFont](#getlogfont)|に、 `LOGFONT` オブジェクトにアタッチされている論理フォントに関する情報を格納 `CFont` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CFont:: operator HFONT](#operator_hfont)|オブジェクトにアタッチされている Windows GDI フォントハンドルを返し `CFont` ます。|

## <a name="remarks"></a>解説

オブジェクトを使用するには `CFont` 、 `CFont` オブジェクトを構築し、 [createfont](#createfont)、 [createfontindirect](#createfontindirect)、 [Createpointfont](#createpointfont)、または [Createpointfontindirect](#createpointfontindirect)を使用してオブジェクトに Windows フォントをアタッチし、オブジェクトのメンバー関数を使用してフォントを操作します。

`CreatePointFont`および関数は、 `CreatePointFontIndirect` `CreateFont` `CreateFontIndirect` ポイントサイズから論理単位に自動的にフォントの高さを変換するため、またはより簡単に使用できます。

の詳細につい `CFont` ては、「 [グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cfontcfont"></a><a name="cfont"></a> CFont:: CFont

`CFont` オブジェクトを構築します。

```
CFont();
```

### <a name="remarks"></a>解説

結果のオブジェクトは `CreateFont` 、使用する前に、、、またはで初期化する必要があり `CreateFontIndirect` `CreatePointFont` `CreatePointFontIndirect` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a> CFont:: CreateFont

指定し `CFont` た特性を使用してオブジェクトを初期化します。

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
フォントの必要な高さ (論理単位) を指定します。 `lfHeight`説明については、Windows SDK の[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体のメンバーを参照してください。 *NHeight* の絶対値は、変換後に16384デバイスユニットを超えることはできません。 すべての高さの比較で、フォントマッパーは、要求されたサイズを超えない最大のフォント、またはすべてのフォントが要求されたサイズを超えた場合に最小のフォントを検索します。

*nWidth*<br/>
フォントの文字の平均幅 (論理単位) を指定します。 *NWidth* が0の場合、デバイスの縦横比が、使用可能なフォントのデジタル化された縦横比と照合され、最も近い一致が検索されます。これは、差分の絶対値によって決まります。

*nEscapement*<br/>
傾斜ベクターとディスプレイサーフェイスの x 軸の間の角度 (0.1 度単位) を指定します。 傾斜ベクターは、行の最初と最後の文字の原点を通る線です。 角度は、x 軸から反時計回りに計測されます。 `lfEscapement` `LOGFONT` 詳細については、Windows SDK の構造体のメンバーを参照してください。

*nOrientation*<br/>
文字のベースラインと x 軸の間の角度 (0.1 度単位) を指定します。 角度は、y 方向が上にある座標系の y 方向が下向きで x 軸から時計回りになる座標系の x 軸から反時計回りに計測されます。

*nWeight*<br/>
フォントの太さ (1000 あたりインク付きピクセル単位) を指定します。  `LOGFONT` 詳細については、Windows SDK の構造体の lfWeight メンバーを参照してください。 説明されている値は概数です。実際の外観は、タイプフェイスによって異なります。 一部のフォントには、FW_NORMAL、FW_REGULAR、および FW_BOLD の重みしかありません。 FW_DONTCARE が指定されている場合は、既定の重みが使用されます。

*bItalic*<br/>
フォントを斜体にするかどうかを指定します。

*bUnderline*<br/>
フォントを下線付きにするかどうかを指定します。

*cStrikeOut*<br/>
フォントの文字を取り消してもよいかどうかを指定します。0以外の値に設定されている場合は、取り消し線のフォントを指定します。

*nCharSet*<br/>
フォントの文字セットを指定し `lfCharSet` `LOGFONT` ます。値の一覧については、Windows SDK の構造体でメンバーを参照してください。

OEM 文字セットはシステムに依存します。

他の文字セットを含むフォントがシステムに存在する可能性があります。 文字セットが不明なフォントを使用するアプリケーションでは、そのフォントで表示される文字列の変換または解釈を試行しないでください。 代わりに、文字列を出力デバイスドライバーに直接渡す必要があります。

フォントマッパーでは、DEFAULT_CHARSET 値は使用されません。 アプリケーションでこの値を使用して、フォントの名前とサイズが論理フォントを完全に記述できるようにすることができます。 指定した名前のフォントが存在しない場合は、任意の文字セットのフォントを指定したフォントに置き換えることができます。 予期しない結果を避けるために、アプリケーションでは DEFAULT_CHARSET 値を控えめに使用する必要があります。

*nOutPrecision*<br/>
目的の出力精度を指定します。 出力精度は、要求されたフォントの高さ、幅、文字の向き、傾斜、およびピッチとどの程度一致する必要があるかを定義します。 `lfOutPrecision` `LOGFONT` 値の一覧と詳細情報については、Windows SDK の構造体のメンバーを参照してください。

*nClipPrecision*<br/>
目的のクリッピング精度を指定します。 クリッピング精度は、クリッピング領域の外側にある文字をクリップする方法を定義します。 `lfClipPrecision` `LOGFONT` 値の一覧については、Windows SDK の構造体のメンバーを参照してください。

埋め込み読み取り専用フォントを使用するには、アプリケーションで CLIP_ENCAPSULATE を指定する必要があります。

デバイス、TrueType、ベクターフォントの一貫したローテーションを実現するために、アプリケーションでは、または演算子を使用して、CLIP_LH_ANGLES 値と他の任意の *nClipPrecision* 値を組み合わせることができます。 CLIP_LH_ANGLES ビットが設定されている場合、すべてのフォントの回転は、座標系の向きが左ききか右ききかによって異なります。 (座標系の向きの詳細については、 *Norientation* パラメーターの説明を参照してください)。CLIP_LH_ANGLES が設定されていない場合、デバイスフォントは常に反時計回りに回転しますが、他のフォントの回転は座標系の向きに依存します。

*nQuality*<br/>
フォントの出力品質を指定します。これにより、GDI が論理フォント属性を実際の物理フォントの属性と一致させるために必要な方法が定義されます。 `lfQuality` `LOGFONT` 値の一覧については、Windows SDK の構造体のメンバーを参照してください。

*nPitchAndFamily*<br/>
フォントのピッチとファミリを指定します。 `lfPitchAndFamily` `LOGFONT` 値の一覧と詳細情報については、Windows SDK の構造体のメンバーを参照してください。

*lpszFacename*<br/>
`CString`フォントのタイプフェイス名を指定する、null で終わる文字列へのポインター。 この文字列の長さは30文字以下でなければなりません。 Windows [Enumfontfamilies](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw) 関数を使用すると、現在使用可能なすべてのフォントを列挙できます。 *Lpszfacename* が NULL の場合、GDI はデバイスに依存しないタイプフェイスを使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、その後、任意のデバイスコンテキストのフォントとして選択できます。

関数は、 `CreateFont` 新しい WINDOWS GDI フォントを作成しません。 GDI で使用可能な物理フォントから最も近い一致を選択するだけです。

アプリケーションでは、論理フォントを作成するときにほとんどのパラメーターに既定の設定を使用できます。 常に特定の値を指定する必要があるパラメーターは、 *nHeight* と *lpszfacename* です。 *NHeight* と *lpszfacename* がアプリケーションによって設定されていない場合、作成される論理フォントはデバイスに依存します。

`CFont`関数によって作成されたオブジェクトが終了したら `CreateFont` 、を使用して `CDC::SelectObject` デバイスコンテキストに別のフォントを選択し、不要になったオブジェクトを削除し `CFont` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a> CFont:: CreateFontIndirect

`CFont` [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体で指定された特性を使用してオブジェクトを初期化します。

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>パラメーター

*lpLogFont*<br/>
`LOGFONT`論理フォントの特性を定義する構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、その後、任意のデバイスの現在のフォントとして選択できます。

このフォントには、 [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 構造体で指定されている特性があります。 [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject)メンバー関数を使用してフォントを選択すると、GDI フォントマッパーは論理フォントと既存の物理フォントを一致させようとします。 フォントマッパーが論理フォントと完全に一致するものを見つけることができない場合は、要求された特性の多くを可能な限り満たす代替フォントが提供されます。

`CFont`関数によって作成されたオブジェクトが不要になったら `CreateFontIndirect` 、を使用してデバイスコンテキストに別のフォントを選択し、不要になっ `CDC::SelectObject` たオブジェクトを削除し `CFont` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a> CFont:: CreatePointFont

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
`CString`フォントのタイプフェイス名を指定する、null で終わる文字列へのポインター。 この文字列の長さは30文字以下でなければなりません。 Windows の EnumFontFamilies 関数を使用すると、現在使用可能なすべてのフォントを列挙できます。 *Lpszfacename* が NULL の場合、GDI はデバイスに依存しないタイプフェイスを使用します。

*pDC*<br/>
*NPointSize* の高さを論理単位に変換するために使用される [CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 NULL の場合、変換には画面デバイスコンテキストが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

*PDC* によってポイントされている CDC オブジェクトを使用して、 *nPointSize* の高さを論理単位に自動的に変換します。

`CFont`関数によって作成されたオブジェクトが完成したら `CreatePointFont` 、まず、デバイスコンテキストからフォントを選択してから、オブジェクトを削除し `CFont` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a> CFont:: CreatePointFontIndirect

この関数は[](#createfontindirect) `lfHeight` 、のメンバーが `LOGFONT` デバイス単位ではなく1/10 ポイントで解釈される点を除いて、createfontindirect と同じです。

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>パラメーター

*lpLogFont*<br/>
論理フォントの特性を定義する [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 構造体を指します。 `lfHeight`構造体のメンバーは、 `LOGFONT` 論理単位ではなく、1/10 ポイントで測定されます。 (たとえば、 `lfHeight` 12 ポイントのフォントを要求するには、を120に設定します)。

*pDC*<br/>
の高さを論理単位に変換するために使用される [CDC](../../mfc/reference/cdc-class.md) オブジェクトへのポインター `lfHeight` 。 NULL の場合、変換には画面デバイスコンテキストが使用されます。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

この関数 `lfHeight` は、構造体を Windows に渡す前に *pDC* が指す CDC オブジェクトを使用して、の高さを論理単位に自動的に変換し `LOGFONT` ます。

`CFont`関数によって作成されたオブジェクトが完成したら `CreatePointFontIndirect` 、まず、デバイスコンテキストからフォントを選択してから、オブジェクトを削除し `CFont` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a> CFont:: FromHandle

`CFont`WINDOWS GDI フォントオブジェクトの HFONT ハンドルが指定された場合に、オブジェクトへのポインターを返します。

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>パラメーター

*hFont*<br/>
Windows フォントを扱う HFONT ハンドル。

### <a name="return-value"></a>戻り値

成功した場合はオブジェクトへのポインター、 `CFont` それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CFont`オブジェクトがハンドルにまだアタッチされていない場合は、一時 `CFont` オブジェクトが作成され、アタッチされます。 この一時 `CFont` オブジェクトは、アプリケーションが次にそのイベントループ内でアイドル状態になったときにのみ有効です。その時点で、すべての一時グラフィックオブジェクトが削除されます。 これを言うもう1つの方法は、一時オブジェクトが、1つのウィンドウメッセージの処理中にのみ有効であることです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a> CFont:: GetLogFont

の構造体のコピーを取得するには、この関数を呼び出し `LOGFONT` `CFont` ます。

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>パラメーター

*pLogFont*<br/>
フォント情報を受け取る [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) 構造体へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外。それ以外の場合は0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a> CFont:: operator HFONT

オブジェクトにアタッチされているフォントの Windows GDI ハンドルを取得するには、この演算子を使用し `CFont` ます。

```
operator HFONT() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、にアタッチされた Windows GDI フォントオブジェクトのハンドル `CFont` 。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、からフォントやテキストへの変換に自動的に使用されるため `CFont` 、 [](/windows/win32/gdi/fonts-and-text) `CFont` hfonts を想定している関数にオブジェクトを渡すことができます。

グラフィックオブジェクトの使用方法の詳細については、「Windows SDK の [グラフィックオブジェクト](/windows/win32/gdi/graphic-objects) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
