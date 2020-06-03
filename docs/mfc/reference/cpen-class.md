---
title: Cペンクラス
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
ms.openlocfilehash: e15dc53fafa0d80f1b52b3fe77f3635c592a4346
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364081"
---
# <a name="cpen-class"></a>Cペンクラス

Windows のグラフィック デバイス インターフェイス (GDI) のペンをカプセル化したものです。

## <a name="syntax"></a>構文

```
class CPen : public CGdiObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cペン::Cペン](#cpen)|`CPen` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cペン::作成ペン](#createpen)|指定したスタイル、幅、およびブラシの属性を使用して、論理コスメティック ペンまたはジオメトリック`CPen`ペンを作成し、オブジェクトにアタッチします。|
|[CPen::作成ペンインダイレクト](#createpenindirect)|[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)構造体で指定されたスタイル、幅、色を使用してペンを作成し、オブジェクトに`CPen`アタッチします。|
|[CPen::ハンドルから](#fromhandle)|Windows HPEN`CPen`が与えられた場合、オブジェクトへのポインターを返します。|
|[Cペン::ゲットエクスキープログペン](#getextlogpen)|[基になる](/windows/win32/api/wingdi/ns-wingdi-extlogpen)構造体を取得します。|
|[Cペン::ゲットログペン](#getlogpen)|基になる[構造を取得](/windows/win32/api/wingdi/ns-wingdi-logpen)します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cペン::オペレーターHPEN](#operator_hpen)|オブジェクトにアタッチされた Windows`CPen`ハンドルを返します。|

## <a name="remarks"></a>解説

の使用方法`CPen`の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a>Cペン::Cペン

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

*nペンスタイル*<br/>
ペンのスタイルを指定します。 コンストラクターの最初のバージョンのこのパラメーターは、次のいずれかの値を指定できます。

- PS_SOLID実線ペンを作成します。

- PS_DASH 破線のペンを作成します。 ペンの幅が 1 以下の場合にのみ有効です (デバイス単位)。

- PS_DOT 点線のペンを作成します。 ペンの幅が 1 以下の場合にのみ有効です (デバイス単位)。

- PS_DASHDOT 破線とドットを交互に使用してペンを作成します。 ペンの幅が 1 以下の場合にのみ有効です (デバイス単位)。

- PS_DASHDOTDOT ダッシュと二重ドットを交互に使用してペンを作成します。 ペンの幅が 1 以下の場合にのみ有効です (デバイス単位)。

- PS_NULL null ペンを作成します。

- PS_INSIDEFRAME Windows `Ellipse`GDI 出力関数によって生成される閉じた図形のフレーム内に、外接する四角形`Rectangle`(、、、、、、、、、、、、、、、`RoundRect``Pie`などの`Chord`メンバー関数) を指定する、閉じた図形のフレーム内に線を描画するペンを作成します。 このスタイルを境界の四角形 (`LineTo`たとえば、メンバー関数) を指定しない Windows GDI 出力関数で使用する場合、ペンの描画領域はフレームによって制限されません。

コンストラクターの 2`CPen`番目のバージョンでは、型、スタイル、エンド キャップ、および結合属性の組み合わせを指定します。 各カテゴリの値は、ビットごとの OR 演算子 (&#124;) を使用して結合する必要があります。 ペンタイプは、次のいずれかの値になります。

- PS_GEOMETRIC幾何学的ペンを作成します。

- PS_COSMETIC 化粧ペンを作成します。

   `CPen`コンストラクタの2番目のバージョンでは *、nPenStyle*に次のペンスタイルを追加します。

- PS_ALTERNATE 1 ピクセルおきに設定するペンを作成します。 (このスタイルは、化粧品のペンにのみ適用されます。

- PS_USERSTYLE ユーザーが提供するスタイル配列を使用するペンを作成します。

   エンド キャップには、次のいずれかの値を指定できます。

- PS_ENDCAP_ROUNDエンドキャップは丸い。

- PS_ENDCAP_SQUAREエンドキャップは正方形です。

- PS_ENDCAP_FLATエンドキャップはフラットです。

   結合には、次のいずれかの値を指定できます。

- PS_JOIN_BEVEL結合はベベブされます。

- PS_JOIN_MITER結合は[、SetMiterLimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit)関数によって設定された現在の制限内にある場合にマイターされます。 結合がこの制限を超えると、ベベが表示されます。

- PS_JOIN_ROUND結合はラウンドです。

*n幅*<br/>
ペンの幅を指定します。

- コンストラクターの最初のバージョンでは、この値が 0 の場合、デバイス単位の幅は、マッピング モードに関係なく常に 1 ピクセルです。

- コンストラクタの 2 番目のバージョンでは *、nPenStyle*がPS_GEOMETRIC場合、幅は論理単位で指定されます。 *nPenStyle が*PS_COSMETIC場合、幅を 1 に設定する必要があります。

*Crcolor*<br/>
ペンの RGB カラーを含みます。

*をクリックします。*<br/>
構造体への`LOGBRUSH`ポイント。 *nPenStyle*がPS_COSMETIC場合、`LOGBRUSH`構造体の*lbColor*メンバーはペンの色を指定し、構造体の*lbStyle*メンバーを`LOGBRUSH`BS_SOLIDに設定する必要があります。 *nPenStyle*がPS_GEOMETRIC場合は、すべてのメンバーを使用してペンのブラシ属性を指定する必要があります。

*数形数*<br/>
*lpStyle*配列の長さをダブルワード単位で指定します。 *nPenStyle*がPS_USERSTYLEされていない場合、この値は 0 である必要があります。

*lpスタイル*<br/>
ダブルワード値の配列へのポイント。 最初の値は、ユーザー定義スタイルの最初のダッシュの長さを指定し、2 番目の値は最初のスペースの長さを指定します。 *nPenStyle*がPS_USERSTYLEされていない場合、このポインターは NULL である必要があります。

### <a name="remarks"></a>解説

引数を指定しないコンストラクターを使用する場合は`CPen`、 、`CreatePen``CreatePenIndirect`または`CreateStockObject`メンバー関数を使用して、結果のオブジェクトを初期化する必要があります。

引数を受け取るコンストラクターを使用する場合は、それ以上の初期化は必要ありません。 引数を持つコンストラクターはエラーが発生した場合に例外をスローできますが、引数を持たないコンストラクターは常に成功します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a>Cペン::作成ペン

指定したスタイル、幅、およびブラシの属性を使用して、論理コスメティック ペンまたはジオメトリック`CPen`ペンを作成し、オブジェクトにアタッチします。

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

*nペンスタイル*<br/>
ペンのスタイルを指定します。 使用可能な値のリストについては[、CPen](#cpen)コンストラクターの*nPenStyle*パラメーターを参照してください。

*n幅*<br/>
ペンの幅を指定します。

- の最初の`CreatePen`バージョンでは、この値が 0 の場合、デバイス単位の幅は、マッピング モードに関係なく常に 1 ピクセルです。

- の 2 番目`CreatePen`のバージョンでは *、nPenStyle*がPS_GEOMETRIC場合、幅は論理単位で指定されます。 *nPenStyle が*PS_COSMETIC場合、幅を 1 に設定する必要があります。

*Crcolor*<br/>
ペンの RGB カラーを含みます。

*をクリックします。*<br/>
[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)構造体へのポイント。 *nPenStyle*がPS_COSMETIC場合、`lbColor``LOGBRUSH`構造体のメンバーはペンの色を指定し、構造体の*lbStyle* `LOGBRUSH`メンバーをBS_SOLIDに設定する必要があります。 nPenStyle がPS_GEOMETRIC場合は、すべてのメンバーを使用してペンのブラシ属性を指定する必要があります。

*数形数*<br/>
*lpStyle*配列の長さをダブルワード単位で指定します。 *nPenStyle*がPS_USERSTYLEされていない場合、この値は 0 である必要があります。

*lpスタイル*<br/>
ダブルワード値の配列へのポイント。 最初の値は、ユーザー定義スタイルの最初のダッシュの長さを指定し、2 番目の値は最初のスペースの長さを指定します。 *nPenStyle*がPS_USERSTYLEされていない場合、このポインターは NULL である必要があります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外、メソッドが失敗した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

の最初の`CreatePen`バージョンでは、指定したスタイル、幅、および色でペンを初期化します。 その後、任意のデバイス コンテキストの現在のペンとしてペンを選択できます。

幅が 1 ピクセルを超えるペンには、常にPS_NULL、PS_SOLID、またはPS_INSIDEFRAMEスタイルを使用する必要があります。

ペンにPS_INSIDEFRAMEスタイルと、論理カラーテーブルの色と一致しない色がある場合、ペンはディザリングされた色で描画されます。 PS_SOLIDペンスタイルを使用して、ディザカラーのペンを作成することはできません。 PS_INSIDEFRAMEスタイルは、ペンの幅が 1 以下の場合にPS_SOLIDと同じです。

の 2`CreatePen`番目のバージョンでは、指定されたスタイル、幅、およびブラシの属性を持つ論理コスメティック またはジオメトリック ペンを初期化します。 コスメティックペンの幅は常に 1 です。ジオメトリック ペンの幅は、常にワールド単位で指定されます。 アプリケーションは、論理ペンを作成した後[、CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject)関数を呼び出すことによって、デバイス コンテキストにそのペンを選択できます。 ペンをデバイス コンテキストに選択した後、ペンを使用して直線や曲線を描画できます。

- *nPenStyle*がPS_COSMETICされ、PS_USERSTYLE場合 *、lpStyle*配列のエントリは、スタイル単位でダッシュとスペースの長さを指定します。 スタイル単位は、ペンを使用して線を描画するデバイスによって定義されます。

- *nPenStyle*がPS_GEOMETRICされ、PS_USERSTYLE場合 *、lpStyle*配列のエントリは、論理単位でダッシュとスペースの長さを指定します。

- *nPenStyle*がPS_ALTERNATE場合、スタイル単位は無視され、他のすべてのピクセルが設定されます。

アプリケーションが指定されたペンを必要としなくなった場合は[、CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数を呼び`CPen`出すか、リソースが使用されないようにオブジェクトを破棄する必要があります。 デバイス コンテキストでペンが選択されている場合、アプリケーションはペンを削除しないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::作成ペンインダイレクト

*lpLogPen*が指す構造体に指定されたスタイル、幅、および色を持つペンを初期化します。

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>パラメーター

*lpLogPen*<br/>
ペンに関する情報を含む Windows[の LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

幅が 1 ピクセルを超えるペンには、常にPS_NULL、PS_SOLID、またはPS_INSIDEFRAMEスタイルを使用する必要があります。

ペンにPS_INSIDEFRAMEスタイルと、論理カラーテーブルの色と一致しない色がある場合、ペンはディザリングされた色で描画されます。 ペンの幅が 1 以下の場合、PS_INSIDEFRAMEスタイルはPS_SOLIDと同じになります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a>CPen::ハンドルから

Windows GDI`CPen`ペン オブジェクトへのハンドルを渡されたオブジェクトへのポインターを返します。

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>パラメーター

*hPen*<br/>
`HPEN`Windows GDI ペンへのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は`CPen`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`CPen` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CPen` オブジェクトが生成され、関連付けられます。 この一`CPen`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは、1 つのウィンドウ メッセージの処理中にのみ有効です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a>Cペン::ゲットエクスキープログペン

基になる`EXTLOGPEN`構造体を取得します。

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*ペ・ログペン*<br/>
ペンに関する情報を含む[EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この`EXTLOGPEN`構造体は、ペンのスタイル、幅、およびブラシの属性を定義します。 たとえば、ペンの`GetExtLogPen`特定のスタイルに一致するように呼び出します。

ペンの属性については、Windows SDK の次のトピックを参照してください。

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [エクスクログペン](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [ログペン](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [押し出しペン](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>例

次のコード例は、ペン`GetExtLogPen`の属性を取得し、同じ色で新しいコスメティック ペンを作成する呼び出しを示しています。

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a>Cペン::ゲットログペン

基になる`LOGPEN`構造体を取得します。

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*ペ・ログペン*<br/>
ペンに関する情報を格納する[LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)構造体へのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この`LOGPEN`構造は、ペンのスタイル、色、パターンを定義します。

たとえば、特定の`GetLogPen`スタイルのペンに一致するように呼び出します。

ペンの属性については、Windows SDK の次のトピックを参照してください。

- [Getobject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [ログペン](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>例

次のコード例は、ペン`GetLogPen`文字を取得し、同じ色で新しいソリッド ペンを作成する呼び出しを示しています。

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a>Cペン::オペレーターHPEN

オブジェクトのアタッチされた Windows GDI`CPen`ハンドルを取得します。

```
operator HPEN() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表される Windows GDI`CPen`オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HPEN オブジェクトの直接使用をサポートするキャスト演算子です。

グラフィック オブジェクトの使用の詳細については、「Windows SDK の[グラフィック オブジェクト](/windows/win32/gdi/graphic-objects)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>関連項目

[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CBrush クラス](../../mfc/reference/cbrush-class.md)
