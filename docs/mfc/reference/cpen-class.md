---
description: '詳細情報: CPen クラス'
title: CPen クラス
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: b85e0de8a5ce9048851b3f0a8ee5a701e749f0af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345148"
---
# <a name="cpen-class"></a>CPen クラス

Windows のグラフィック デバイス インターフェイス (GDI) のペンをカプセル化したものです。

## <a name="syntax"></a>構文

```
class CPen : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPen:: CPen](#cpen)|`CPen` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPen:: CreatePen](#createpen)|スタイル、幅、ブラシの属性を指定して論理コスメティックペンまたはジオメトリックペンを作成し、オブジェクトにアタッチし `CPen` ます。|
|[CPen:: Createを間接的に](#createpenindirect)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)構造体で指定されたスタイル、幅、および色でペンを作成し、オブジェクトにアタッチし `CPen` ます。|
|[CPen:: FromHandle](#fromhandle)|`CPen`Windows HPEN が指定された場合に、オブジェクトへのポインターを返します。|
|[CPen:: GetExtLogPen](#getextlogpen)|基になる [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 構造体を取得します。|
|[CPen:: GetLogPen](#getlogpen)|基になる [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 構造体を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPen:: operator HPEN](#operator_hpen)|オブジェクトにアタッチされている Windows ハンドルを返し `CPen` ます。|

## <a name="remarks"></a>解説

の使用方法の詳細について `CPen` は、「 [グラフィックオブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a> CPen:: CPen

`CPen` オブジェクトを構築します。

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*Nペンスタイル*<br/>
ペンのスタイルを指定します。 コンストラクターの最初のバージョンのこのパラメーターには、次のいずれかの値を指定できます。

- PS_SOLID は、ソリッドペンを作成します。

- PS_DASH によって破線のペンが作成されます。 デバイス単位で、ペンの幅が1以下の場合にのみ有効です。

- PS_DOT は点線のペンを作成します。 デバイス単位で、ペンの幅が1以下の場合にのみ有効です。

- PS_DASHDOT は、ダッシュとドットを交互に使用してペンを作成します。 デバイス単位で、ペンの幅が1以下の場合にのみ有効です。

- PS_DASHDOTDOT は、ダッシュと2つのドットを交互に使用してペンを作成します。 デバイス単位で、ペンの幅が1以下の場合にのみ有効です。

- PS_NULL によって NULL ペンが作成されます。

- PS_INSIDEFRAME は、外接する四角形 (、、 `Ellipse` `Rectangle` 、、 `RoundRect` `Pie` およびメンバー関数など `Chord` ) を指定する Windows GDI 出力関数によって生成される、閉じた図形のフレーム内に線を描画するペンを作成します。 このスタイルが、外接する四角形を指定していない Windows GDI 出力関数 (たとえば、メンバー関数) で使用されている場合 `LineTo` 、ペンの描画領域はフレームによって制限されません。

コンストラクターの2番目のバージョンは、 `CPen` 型、スタイル、エンドキャップ、および結合属性の組み合わせを指定します。 各カテゴリの値は、ビットごとの OR 演算子 (&#124;) を使用して結合する必要があります。 ペンの種類には、次のいずれかの値を指定できます。

- PS_GEOMETRIC ジオメトリックペンを作成します。

- PS_COSMETIC は、コスメティックペンを作成します。

   コンストラクターの2番目のバージョンは、 `CPen` *Npenstyle* 用の次のペンスタイルを追加します。

- PS_ALTERNATE は、他のすべてのピクセルを設定するペンを作成します。 (このスタイルは、コスメティックペンにのみ適用できます。)

- PS_USERSTYLE は、ユーザーが指定したスタイル配列を使用するペンを作成します。

   終了キャップには、次のいずれかの値を指定できます。

- PS_ENDCAP_ROUND エンドキャップは ROUND です。

- PS_ENDCAP_SQUARE エンドキャップは正方形です。

- PS_ENDCAP_FLAT エンドキャップはフラットです。

   結合には、次のいずれかの値を指定できます。

- PS_JOIN_BEVEL 結合には傾斜があります。

- PS_JOIN_MITER の結合は、 [Setmare limit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) 関数によって設定された現在の制限内にあるときに、マイタされます。 結合がこの制限を超えると、傾斜します。

- PS_JOIN_ROUND 結合は ROUND です。

*nWidth*<br/>
ペンの幅を指定します。

- コンストラクターの最初のバージョンでは、この値が0の場合、デバイス単位の幅は、マッピングモードに関係なく、常に1ピクセルになります。

- コンストラクターの2番目のバージョンでは、 *Npenstyle* が PS_GEOMETRIC の場合、幅は論理単位で指定されます。 *Npenstyle* が PS_COSMETIC の場合、幅を1に設定する必要があります。

*crColor*<br/>
ペンの RGB 色を格納します。

*pLogBrush*<br/>
`LOGBRUSH`構造体を指します。 *NlbColor style* が PS_COSMETIC の場合、構造体のメンバーは、 `LOGBRUSH` ペンの色を指定し、構造体の *lbStyle* メンバーを `LOGBRUSH` BS_SOLID に設定する必要があります。 *Npenstyle* が PS_GEOMETRIC 場合は、すべてのメンバーを使用して、ペンのブラシ属性を指定する必要があります。

*nStyleCount*<br/>
*Lpstyle* 配列の長さをダブルワード単位で指定します。 *Npenstyle* が PS_USERSTYLE ない場合、この値は0である必要があります。

*lpStyle*<br/>
ダブルワード値の配列を指します。 最初の値は、ユーザー定義スタイルの最初のダッシュの長さを指定し、2番目の値は最初のスペースの長さを指定します。 *Npenstyle* が PS_USERSTYLE ない場合、このポインターは NULL である必要があります。

### <a name="remarks"></a>解説

引数を指定せずにコンストラクターを使用する場合は `CPen` `CreatePen` 、、 `CreatePenIndirect` 、またはのメンバー関数を使用して、結果のオブジェクトを初期化する必要があり `CreateStockObject` ます。

引数を受け取るコンストラクターを使用する場合、それ以上の初期化は必要ありません。 引数を持つコンストラクターは、エラーが発生した場合は例外をスローできますが、引数を持たないコンストラクターは常に成功します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a> CPen:: CreatePen

スタイル、幅、ブラシの属性を指定して論理コスメティックペンまたはジオメトリックペンを作成し、オブジェクトにアタッチし `CPen` ます。

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*Nペンスタイル*<br/>
ペンのスタイルを指定します。 使用可能な値の一覧については、「 [CPen](#cpen)コンストラクター」の *nのスタイル* パラメーターを参照してください。

*nWidth*<br/>
ペンの幅を指定します。

- の最初のバージョンでは `CreatePen` 、この値が0の場合、デバイス単位の幅は、マッピングモードに関係なく、常に1ピクセルになります。

- 2番目のバージョンのでは、 `CreatePen` *Npenstyle* が PS_GEOMETRIC の場合、幅は論理単位で指定されます。 *Npenstyle* が PS_COSMETIC の場合、幅を1に設定する必要があります。

*crColor*<br/>
ペンの RGB 色を格納します。

*pLogBrush*<br/>
[Logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体を指します。 *NlbStyle style* が PS_COSMETIC の場合、 `lbColor` 構造体のメンバーは `LOGBRUSH` ペンの色を指定し、構造体のメンバーは `LOGBRUSH` BS_SOLID に設定する必要があります。 NPenStyle が PS_GEOMETRIC 場合は、すべてのメンバーを使用して、ペンのブラシ属性を指定する必要があります。

*nStyleCount*<br/>
*Lpstyle* 配列の長さをダブルワード単位で指定します。 *Npenstyle* が PS_USERSTYLE ない場合、この値は0である必要があります。

*lpStyle*<br/>
ダブルワード値の配列を指します。 最初の値は、ユーザー定義スタイルの最初のダッシュの長さを指定し、2番目の値は最初のスペースの長さを指定します。 *Npenstyle* が PS_USERSTYLE ない場合、このポインターは NULL である必要があります。

### <a name="return-value"></a>戻り値

成功した場合は0以外の値。メソッドが失敗した場合は0。

### <a name="remarks"></a>解説

最初のバージョンのでは、 `CreatePen` 指定されたスタイル、幅、および色でペンが初期化されます。 ペンは、その後、任意のデバイスコンテキストの現在のペンとして選択できます。

幅が1ピクセルを超えるペンは、常に PS_NULL、PS_SOLID、または PS_INSIDEFRAME スタイルである必要があります。

ペンの PS_INSIDEFRAME スタイルと、論理カラーテーブルの色に一致しない色がある場合、ペンはディザーカラーで描画されます。 PS_SOLID ペンスタイルを使用して、ディザーカラーでペンを作成することはできません。 PS_INSIDEFRAME スタイルは、ペンの幅が1以下の場合に PS_SOLID と同じです。

2番目のバージョンのは、 `CreatePen` 指定されたスタイル、幅、ブラシの属性を持つ論理コスメティックペンまたはジオメトリックペンを初期化します。 コスメティックペンの幅は常に1です。ジオメトリックペンの幅は、常にワールド単位で指定されます。 アプリケーションは、論理ペンを作成した後、 [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) 関数を呼び出すことによって、そのペンをデバイスコンテキストに選択できます。 デバイスコンテキストにペンを選択すると、そのペンを使用して直線と曲線を描画できます。

- *Npenstyle* が PS_COSMETIC および PS_USERSTYLE の場合、 *lpstyle* 配列内のエントリは、スタイル単位のダッシュと空白の長さを指定します。 スタイル単位は、ペンを使用して線を描画するデバイスによって定義されます。

- *Npenstyle* が PS_GEOMETRIC および PS_USERSTYLE の場合、 *lpstyle* 配列内のエントリは、論理単位のダッシュとスペースの長さを指定します。

- *Npenstyle* が PS_ALTERNATE 場合、スタイルの単位は無視され、他のすべてのピクセルが設定されます。

アプリケーションで特定のペンが不要になった場合は、 [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) メンバー関数を呼び出すか、 `CPen` リソースが使用されなくなるようにオブジェクトを破棄する必要があります。 アプリケーションでは、ペンがデバイスコンテキストで選択されている場合、ペンを削除しないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a> CPen:: Createを間接的に

*L道路 Gpen* が指す構造体で指定されたスタイル、幅、および色を持つペンを初期化します。

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>パラメーター

*L道路 Gpen*<br/>
ペンに関する情報を格納している Windows [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

幅が1ピクセルを超えるペンは、常に PS_NULL、PS_SOLID、または PS_INSIDEFRAME スタイルである必要があります。

ペンの PS_INSIDEFRAME スタイルと、論理カラーテーブルの色に一致しない色がある場合、ペンはディザーカラーで描画されます。 PS_INSIDEFRAME スタイルは、ペンの幅が1以下の場合に PS_SOLID と同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a> CPen:: FromHandle

`CPen`WINDOWS GDI ペンオブジェクトへのハンドルを指定して、オブジェクトへのポインターを返します。

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>パラメーター

*hPen*<br/>
`HPEN` Windows GDI ペンに対するハンドル。

### <a name="return-value"></a>戻り値

成功した場合はオブジェクトへのポインター、 `CPen` それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CPen` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CPen` オブジェクトが生成され、関連付けられます。 この一時 `CPen` オブジェクトは、アプリケーションが次にそのイベントループ内でアイドル状態になったときにのみ有効です。その時点で、すべての一時グラフィックオブジェクトが削除されます。 つまり、一時オブジェクトは、1つのウィンドウメッセージの処理中にのみ有効です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a> CPen:: GetExtLogPen

基に `EXTLOGPEN` なる構造体を取得します。

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*一括配信*<br/>
ペンに関する情報を格納している [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`EXTLOGPEN`構造体は、ペンのスタイル、幅、ブラシの属性を定義します。 たとえば、を呼び出して、 `GetExtLogPen` ペンの特定のスタイルに一致させます。

ペン属性の詳細については、Windows SDK の次のトピックを参照してください。

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [ExtCreatePen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>例

次のコード例は、 `GetExtLogPen` を呼び出して、ペンの属性を取得し、同じ色で新しいコスメティックペンを作成する方法を示しています。

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a> CPen:: GetLogPen

基に `LOGPEN` なる構造体を取得します。

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*一括配信*<br/>
ペンに関する情報を格納する [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 構造体を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`LOGPEN`構造体は、ペンのスタイル、色、およびパターンを定義します。

たとえば、を呼び出して、 `GetLogPen` 特定の種類のペンに一致させます。

ペン属性の詳細については、Windows SDK の次のトピックを参照してください。

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>例

次のコード例では、 `GetLogPen` を呼び出して、ペン文字を取得し、同じ色で新しいソリッドペンを作成する方法を示します。

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a> CPen:: operator HPEN

オブジェクトのアタッチされた Windows GDI ハンドルを取得し `CPen` ます。

```
operator HPEN() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI オブジェクトへのハンドル `CPen` 。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HPEN オブジェクトの直接使用をサポートするキャスト演算子です。

グラフィックオブジェクトの使用方法の詳細については、「Windows SDK の [グラフィックオブジェクト](/windows/win32/gdi/graphic-objects) 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>関連項目

[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CBrush クラス](../../mfc/reference/cbrush-class.md)
