---
title: Cフォントクラス
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
ms.openlocfilehash: 36fd469b182d5f3e0d3449112d04c1a8623d7526
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373838"
---
# <a name="cfont-class"></a>Cフォントクラス

Windows のグラフィック デバイス インターフェイス (GDI) のフォントをカプセル化したもので、フォントを操作するメンバー関数を提供します。

## <a name="syntax"></a>構文

```
class CFont : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cフォント::Cフォント](#cfont)|`CFont` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cフォント::フォントを作成します。](#createfont)|指定した特性`CFont`を持つを初期化します。|
|[Cフォント::フォントインダイレクトを作成します。](#createfontindirect)|構造体に指定`CFont`された特性を使用してオブジェクトを`LOGFONT`初期化します。|
|[Cフォント::作成ポイントフォント](#createpointfont)|`CFont`指定した高さ、10 分の 1 のポイント、および書体を初期化します。|
|[Cフォント::ダイレクトポイントフォント](#createpointfontindirect)|フォントの`CreateFontIndirect`高さは、論理単位ではなく 10 分の 1 のポイントで測定される点を除いて同じです。|
|[Cフォント::ハンドルから](#fromhandle)|Windows HFONT`CFont`が指定されたときにオブジェクトへのポインターを返します。|
|[Cフォント::ゲットログフォント](#getlogfont)|`CFont`オブジェクトに`LOGFONT`アタッチされている論理フォントに関する情報を a に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cフォント::演算子HFONT](#operator_hfont)|オブジェクトにアタッチされた Windows GDI`CFont`フォント ハンドルを返します。|

## <a name="remarks"></a>解説

オブジェクトを`CFont`使用するには、オブジェクトを`CFont`作成し、そのオブジェクトに Windows[フォントを](#createpointfontindirect)アタッチ[CreateFontIndirect](#createfontindirect)するには、そのオブジェクトに[CreatePointFont](#createpointfont)[フォント](#createfont)を追加します。

`CreatePointFont`および`CreatePointFontIndirect`関数は、フォントの高さを`CreateFont`ポイント`CreateFontIndirect`サイズから論理単位に自動的に変換するため、使用する方が簡単です。

の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。 `CFont`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CFont`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cfontcfont"></a><a name="cfont"></a>Cフォント::Cフォント

`CFont` オブジェクトを構築します。

```
CFont();
```

### <a name="remarks"></a>解説

生成`CreateFont`されるオブジェクトは、 、 `CreateFontIndirect`、 `CreatePointFont`、 `CreatePointFontIndirect` 、 、 、 で初期化する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]

## <a name="cfontcreatefont"></a><a name="createfont"></a>Cフォント::フォントを作成します。

指定した特性`CFont`を持つオブジェクトを初期化します。

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
フォントの必要な高さを論理単位で指定します。 詳細については`lfHeight`、Windows SDK の[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体のメンバーを参照してください。 *nHeight*の絶対値は、変換後に 16,384 デバイス単位を超えてはなりません。 すべての高さの比較では、フォント マッパーは、要求されたサイズを超えない最大のフォントを検索するか、すべてのフォントが要求されたサイズを超えた場合は最小のフォントを探します。

*n幅*<br/>
フォントの文字の平均幅 (論理単位) を指定します。 *nWidth が*0 の場合、デバイスの縦横比は、使用可能なフォントのデジタル化縦横比と一致して、差の絶対値によって決定される最も近いフォントを見つけます。

*nエスケープメント*<br/>
表示サーフェスの x 軸との間の角度を 0.1 度単位で指定します。 エスケープメント ベクトルは、行の最初と最後の文字の原点を通る行です。 角度は x 軸から反時計回りに計測されます。 詳細については`lfEscapement`、Windows `LOGFONT` SDK の構造体のメンバーを参照してください。

*nオリエンテーション*<br/>
文字のベースラインと x 軸の間の角度を 0.1 度単位で指定します。 Y 方向が下降している座標系の場合は、x 軸から反時計回りに計測され、Y 方向が上がっている座標系の場合は X 軸から時計回りに計測されます。

*n重量*<br/>
フォントの太さを指定します (インクピクセルで 1000 あたり)。 詳細については、Windows SDK`LOGFONT`の構造体の*lfWeight*メンバーを参照してください。 記述された値は近似値です。実際の外観は書体によって異なります。 フォントによっては、FW_NORMAL、FW_REGULAR、およびFW_BOLDの重みしか持っていないものがあります。 FW_DONTCAREを指定すると、既定の重みが使用されます。

*bItalic*<br/>
フォントが斜体であるかどうかを指定します。

*b アンダーライン*<br/>
フォントに下線を付けるかどうかを指定します。

*クストライクアウト*<br/>
フォントの文字を取り消すかどうかを指定します。0 以外の値に設定されている場合は、取り消しフォントを指定します。

*nCharセット*<br/>
フォントの文字セットを指定する Windows `lfCharSet` SDK`LOGFONT`の構造体のメンバーを参照して、値のリストを確認します。

OEM 文字セットはシステムに依存します。

他の文字セットを持つフォントは、システムに存在する場合があります。 不明な文字セットを持つフォントを使用するアプリケーションは、そのフォントでレンダリングされる文字列を変換または解釈しようとしないでください。 代わりに、文字列は出力デバイス ドライバーに直接渡す必要があります。

フォント マッパーはDEFAULT_CHARSET値を使用しません。 アプリケーションはこの値を使用して、フォントの名前とサイズを完全に論理フォントを記述できます。 指定された名前のフォントが存在しない場合は、任意の文字セットのフォントを指定されたフォントに置き換えることができます。 予期しない結果を避けるため、アプリケーションではDEFAULT_CHARSET値を控えめに使用する必要があります。

*アウトプレシジョン*<br/>
目的の出力精度を指定します。 出力精度は、出力が要求されたフォントの高さ、幅、文字の向き、エスケープメント、およびピッチとどれだけ近く必要かを定義します。 値の`lfOutPrecision`一覧と`LOGFONT`詳細については、Windows SDK の構造体のメンバーを参照してください。

*nクリップPrecision*<br/>
目的のクリッピング精度を指定します。 クリッピングの精度は、クリッピング領域の一部外にある文字をクリップする方法を定義します。 値の`lfClipPrecision`一覧については`LOGFONT`、Windows SDK の構造体のメンバーを参照してください。

埋め込まれた読み取り専用フォントを使用するには、アプリケーションでCLIP_ENCAPSULATEを指定する必要があります。

デバイス、TrueType、およびベクトル フォントの回転を一貫して実現するために、アプリケーションでは OR 演算子を使用して、CLIP_LH_ANGLES値を他の*nClipPrecision*値と組み合わせることができます。 CLIP_LH_ANGLESビットが設定されている場合、すべてのフォントの回転は、座標系の向きが左利きか右手のどちらであるかによって異なります。 (座標系の方向の詳細については *、nOrientation*パラメータの説明を参照してください)。CLIP_LH_ANGLESが設定されていない場合、デバイス フォントは常に反時計回りに回転しますが、他のフォントの回転は座標系の方向に依存します。

*n品質*<br/>
GDI が論理フォント属性を実際の物理フォントの属性と一致させようとする必要がある場合、フォントの出力品質を指定します。 値の`lfQuality`一覧については`LOGFONT`、Windows SDK の構造体のメンバーを参照してください。

*アンドファミリー*<br/>
フォントのピッチとファミリを指定します。 値の`lfPitchAndFamily`一覧と`LOGFONT`詳細については、Windows SDK の構造体のメンバーを参照してください。

*名前*<br/>
フォント`CString`の書体名を指定する null で終わる文字列へのポインターまたはポインター。 この文字列の長さは 30 文字を超えることはできません。 [関数を](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesw)使用して、現在利用可能なすべてのフォントを列挙できます。 *lpszFacename*が NULL の場合、GDI はデバイスに依存しない書体を使用します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、デバイス コンテキストのフォントとして選択できます。

この`CreateFont`関数は、新しい Windows GDI フォントを作成しません。 GDI で使用できる物理フォントから最も近い一致を選択するだけです。

アプリケーションは、論理フォントを作成するときに、ほとんどのパラメーターにデフォルト設定を使用できます。 常に特定の値を指定する必要があるパラメーターは *、nHeight*と*lpszFacename*です。 *nHeight*および*lpszFacename*がアプリケーションによって設定されていない場合、作成される論理フォントはデバイスに依存します。

関数によって作成されたオブジェクト`CFont`を`CreateFont`使用し終わったら、デバイス`CDC::SelectObject`コンテキストで別のフォントを選択し、不要になったオブジェクト`CFont`を削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]

## <a name="cfontcreatefontindirect"></a><a name="createfontindirect"></a>Cフォント::フォントインダイレクトを作成します。

[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)`CFont`構造体に指定された特性を持つオブジェクトを初期化します。

```
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
論理フォントの`LOGFONT`特性を定義する構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

フォントは、その後、任意のデバイスの現在のフォントとして選択できます。

このフォントには[、LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体で指定された特性があります。 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject)メンバー関数を使用してフォントを選択すると、GDI フォント マッパーは、既存の物理フォントと論理フォントを一致させようとします。 フォントマッパーが論理フォントと完全に一致するものを見つけられなかった場合、要求された特性のできるだけ多くの特性が一致する代替フォントが提供されます。

関数で作成されたオブジェクトが`CFont`不要になった場合は、デバイス`CDC::SelectObject`コンテキストで別のフォントを選択し、不要になったオブジェクトを`CFont`削除します。 `CreateFontIndirect`

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]

## <a name="cfontcreatepointfont"></a><a name="createpointfont"></a>Cフォント::作成ポイントフォント

この関数は、指定された書体とポイント サイズのフォントを簡単に作成する方法を提供します。

```
BOOL CreatePointFont(
    int nPointSize,
    LPCTSTR lpszFaceName,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
10 分の 1 ポイントのフォントの高さを要求しました。 (たとえば、120 を渡して 12 ポイントのフォントを要求します)。

*名前*<br/>
フォント`CString`の書体名を指定する null で終わる文字列へのポインターまたはポインター。 この文字列の長さは 30 文字を超えることはできません。 Windows '列挙フォントファミリー関数を使用して、現在利用可能なすべてのフォントを列挙できます。 *lpszFaceName*が NULL の場合、GDI はデバイスに依存しない書体を使用します。

*pDC*<br/>
*nPointSize*の高さを論理単位に変換するために使用される[CDC](../../mfc/reference/cdc-class.md)オブジェクトへのポインター。 NULL の場合、画面デバイス コンテキストが変換に使用されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

*pDC*が指す CDC オブジェクトを使用して *、nPointSize*の高さを自動的に論理単位に変換します。

関数によって作成されたオブジェクト`CFont`を`CreatePointFont`使用し終わったら、まずデバイス コンテキストからフォントを選択してから、オブジェクトを`CFont`削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]

## <a name="cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>Cフォント::ダイレクトポイントフォント

この関数は[CreateFontIndirect](#createfontindirect)と同じですが`lfHeight`、メンバー`LOGFONT`はデバイス単位ではなく 10 分の 1 のポイントで解釈されます。

```
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,
    CDC* pDC = NULL);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
論理フォントの特性を定義する[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体へのポイント。 構造体`lfHeight`の`LOGFONT`メンバーは、論理単位ではなく 10 分の 1 のポイントで測定されます。 (たとえば、12`lfHeight`ポイントのフォントを要求するには 120 に設定します)。

*pDC*<br/>
高さを論理単位に変換するために使用される[CDC](../../mfc/reference/cdc-class.md)オブジェクト`lfHeight`へのポインター。 NULL の場合、画面デバイス コンテキストが変換に使用されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

この関数は、構造体を Windows`lfHeight`に渡`LOGFONT`す前に *、pDC*が指す CDC オブジェクトを使用して、高さを自動的に論理単位に変換します。

関数によって作成されたオブジェクト`CFont`を`CreatePointFontIndirect`使用し終わったら、まずデバイス コンテキストからフォントを選択してから、オブジェクトを`CFont`削除します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]

## <a name="cfontfromhandle"></a><a name="fromhandle"></a>Cフォント::ハンドルから

Windows GDI`CFont`フォント オブジェクトへの HFONT ハンドルが与えられた場合、オブジェクトへのポインターを返します。

```
static CFont* PASCAL FromHandle(HFONT hFont);
```

### <a name="parameters"></a>パラメーター

*hフォント*<br/>
Windows フォントへの HFONT ハンドル。

### <a name="return-value"></a>戻り値

成功した場合は`CFont`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

オブジェクトが`CFont`ハンドルにまだアタッチされていない場合は、一時`CFont`オブジェクトが作成され、アタッチされます。 この一`CFont`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 もう 1 つの言い方は、一時オブジェクトが 1 つのウィンドウ メッセージの処理中にのみ有効であるということです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]

## <a name="cfontgetlogfont"></a><a name="getlogfont"></a>Cフォント::ゲットログフォント

の`LOGFONT`構造体のコピーを取得`CFont`します。

```
int GetLogFont(LOGFONT* pLogFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
フォント情報を受け取るための[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体へのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外、それ以外の場合は 0 以外の値を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]

## <a name="cfontoperator-hfont"></a><a name="operator_hfont"></a>Cフォント::演算子HFONT

この演算子を使用して、オブジェクトに添付されているフォントの Windows GDI ハンドルを`CFont`取得します。

```
operator HFONT() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、アタッチされた Windows GDI フォント オブジェクトの`CFont`ハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は`CFont`[フォントおよびテキスト](/windows/win32/gdi/fonts-and-text)への変換に自動的に使用されるため、HFONT`CFont`を想定する関数にオブジェクトを渡すことができます。

グラフィックオブジェクトの使用の詳細については、Windows SDK の[グラフィックオブジェクト](/windows/win32/gdi/graphic-objects)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
