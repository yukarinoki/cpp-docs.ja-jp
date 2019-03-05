---
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
ms.openlocfilehash: 8510c29571e6a370c7948ebe49e53b2c22dbfb9c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293720"
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
|[CPen::CPen](#cpen)|`CPen` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPen::CreatePen](#createpen)|指定したスタイル、幅、およびブラシ属性の論理表面的なまたは幾何学的ペンを作成しにアタッチします、`CPen`オブジェクト。|
|[CPen::CreatePenIndirect](#createpenindirect)|スタイル、幅、および色でペンを作成、 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)構造体、およびにアタッチします、`CPen`オブジェクト。|
|[CPen::FromHandle](#fromhandle)|ポインターを返します、 `CPen` Windows HPEN が指定されるとします。|
|[CPen::GetExtLogPen](#getextlogpen)|取得、[保持](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)構造を基になります。|
|[CPen::GetLogPen](#getlogpen)|取得、 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)構造を基になります。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CPen::operator HPEN](#operator_hpen)|アタッチされている Windows ハンドルを返します、`CPen`オブジェクト。|

## <a name="remarks"></a>Remarks

使用しての詳細については`CPen`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cpen"></a>  CPen::CPen

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

*nPenStyle*<br/>
ペンのスタイルを指定します。 コンス トラクターの最初のバージョンでは、このパラメーターには、次の値のいずれかを指定できます。

- きは、solid ペンを作成します。

- PS_DASH は破線のペンを作成します。 ペンの幅が 1 つ以下、デバイスでのユニットである場合にのみ有効です。

- PS_DOT 点線のペンを作成します。 ペンの幅が 1 つ以下、デバイスでのユニットである場合にのみ有効です。

- 交互に使用するペン ダッシュし、ドット PS_DASHDOT を作成します。 ペンの幅が 1 つ以下、デバイスでのユニットである場合にのみ有効です。

- PS_DASHDOTDOT を代替ダッシュと 2 つのドットを使用するペンを作成します。 ペンの幅が 1 つ以下、デバイスでのユニットである場合にのみ有効です。

- 必ずでは、null のペンを作成します。

- 出力の外接する四角形を指定する関数をペンで閉じた図形のフレーム内の行を描画するペンの生成を作成して Windows GDI (たとえば、 `Ellipse`、 `Rectangle`、 `RoundRect`、 `Pie`、および`Chord`メンバー関数)。 外接する四角形が指定されていない Windows GDI 関数でこのスタイルを使用する場合 (たとえば、`LineTo`メンバー関数)、枠は、ペンの描画領域に制限されません。

2 番目のバージョン、`CPen`コンス トラクターは、種類、スタイル、端点キャップ、および結合の属性の組み合わせを指定します。 各カテゴリの値はビットごとの OR 演算子を使用して結合する必要があります (&#124;)。 ペン型には、次の値のいずれかを指定できます。

- PS_GEOMETRIC は、幾何学的ペンを作成します。

- PS_COSMETIC は表面的なペンを作成します。

   2 番目のバージョン、`CPen`コンス トラクターの次のペンのスタイルを追加します*nPenStyle*:

- PS_ALTERNATE では、その他のすべてのピクセルを設定するペンを作成します。 (このスタイルは、表面的なペンにのみ適用できます)。

- PS_USERSTYLE は、ユーザーが指定したスタイルの配列を使用するペンを作成します。

   端点キャップには、次の値のいずれかを指定できます。

- PS_ENDCAP_ROUND 端点キャップは round です。

- PS_ENDCAP_SQUARE 端点キャップは正方形です。

- PS_ENDCAP_FLAT 端点キャップは一定です。

   結合には、次の値のいずれかを指定できます。

- 斜め PS_JOIN_BEVEL を結合します。

- PS_JOIN_MITER 結合はマイターによって設定された現在の制限内にあるときに、 [SetMiterLimit](/windows/desktop/api/wingdi/nf-wingdi-setmiterlimit)関数。 結合では、この制限を超えている場合は斜めです。

- PS_JOIN_ROUND 結合は、round です。

*nWidth*<br/>
ペンの幅を指定します。

- コンス トラクターの最初のバージョンの場合、この値は 0 で幅をデバイス単位は常にマッピング モードに関係なく、1 ピクセルです。

- コンス トラクターの 2 番目のバージョンの場合*nPenStyle* PS_GEOMETRIC は、論理単位の幅を指定します。 場合*nPenStyle* PS_COSMETIC は、幅を 1 に設定する必要があります。

*crColor*<br/>
ペンの RGB 色が含まれています。

*終了*<br/>
指す、`LOGBRUSH`構造体。 場合*nPenStyle* PS_COSMETIC には、 *lbColor*のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、 *lbStyle*のメンバー、 `LOGBRUSH`構造体は、BS_SOLID に設定する必要があります。 場合*nPenStyle* PS_GEOMETRIC は、すべてのメンバーは、ペンのブラシ属性を指定するために使用する必要があります。

*nStyleCount*<br/>
ダブルワード単位の長さを指定します、 *lpStyle*配列。 この値は場合は 0 である必要があります*nPenStyle* PS_USERSTYLE ではありません。

*lpStyle*<br/>
ダブルワード値の配列を指します。 2 番目の値が最初の空白の長さを指定します、最初の値は、ユーザー定義スタイルで最初のダッシュの長さを指定します。 このポインターは、場合に、NULL にする必要があります*nPenStyle* PS_USERSTYLE ではありません。

### <a name="remarks"></a>Remarks

引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CPen`オブジェクトを`CreatePen`、 `CreatePenIndirect`、または`CreateStockObject`メンバー関数。

引数を受け取るコンス トラクターを使用する場合は、さらに初期化もする必要はありません。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

##  <a name="createpen"></a>  CPen::CreatePen

指定したスタイル、幅、およびブラシ属性の論理表面的なまたは幾何学的ペンを作成しにアタッチします、`CPen`オブジェクト。

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

*nPenStyle*<br/>
ペンのスタイルを指定します。 使用可能な値の一覧は、次を参照してください。、 *nPenStyle*パラメーター、 [CPen](#cpen)コンス トラクター。

*nWidth*<br/>
ペンの幅を指定します。

- 最初のバージョンの`CreatePen`、デバイス単位の幅がマッピング モードに関係なく、1 ピクセルでは常にこの値が 0 の場合。

- 2 番目のバージョンの`CreatePen`場合は、 *nPenStyle* PS_GEOMETRIC は、論理単位の幅を指定します。 場合*nPenStyle* PS_COSMETIC は、幅を 1 に設定する必要があります。

*crColor*<br/>
ペンの RGB 色が含まれています。

*終了*<br/>
指す、 [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)構造体。 場合*nPenStyle* PS_COSMETIC には、`lbColor`のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、 *lbStyle*のメンバー、`LOGBRUSH`うちに構造体を設定する必要があります実線。 NPenStyle が PS_GEOMETRIC の場合は、ペンのブラシ属性を指定するすべてのメンバーを使用する必要があります。

*nStyleCount*<br/>
ダブルワード単位の長さを指定します、 *lpStyle*配列。 この値は場合は 0 である必要があります*nPenStyle* PS_USERSTYLE ではありません。

*lpStyle*<br/>
ダブルワード値の配列を指します。 2 番目の値が最初の空白の長さを指定します、最初の値は、ユーザー定義スタイルで最初のダッシュの長さを指定します。 このポインターは、場合に、NULL にする必要があります*nPenStyle* PS_USERSTYLE ではありません。

### <a name="return-value"></a>戻り値

成功した場合、0 以外の場合、メソッドが失敗した場合は 0。

### <a name="remarks"></a>Remarks

最初のバージョンの`CreatePen`指定したスタイル、幅、および色を使用する、ペンを初期化します。 任意のデバイス コンテキストの現在のペンとペンをその後選択できます。

ペンの幅が 1 ピクセルよりも大きい値には、必ず、きは、またはペン スタイルが常に必要です。

ペンにペン スタイルと色が論理カラー テーブルで使用する色に一致しない場合、ペンをディザリングされた色で描画します。 ディザリングされた色でペンを作成するきはペンのスタイルを使用できません。 ペンの幅が 1 に等しいまたはそれよりも小さい場合は、ペンのスタイルをきと同じです。

2 番目のバージョンの`CreatePen`スタイル、幅、およびブラシ属性の指定した論理表面的なまたは幾何学的ペンを初期化します。 表面的なペンの幅は常に 1 です。ジオメトリのペンの幅は常にワールド単位で指定します。 アプリケーションには、論理ペンが作成されたら、デバイス コンテキストのペンその選択を呼び出して、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)関数。 デバイス コンテキストにペンを選択すると後、は、直線と曲線を描画するために使用できます。

- 場合*nPenStyle* PS_COSMETIC と PS_USERSTYLE、内のエントリには、 *lpStyle*スタイル単位で配列がダッシュと空白の長さを指定します。 スタイル、単位は、ペンが行を描画するために使用されているデバイスによって定義されます。

- 場合*nPenStyle* PS_GEOMETRIC と PS_USERSTYLE、内のエントリには、 *lpStyle*配列は、論理ユニットにダッシュと空白の長さを指定します。

- 場合*nPenStyle* PS_ALTERNATE は、スタイル、単位は無視され他のすべてのピクセルを設定します。

呼び出して不要になった、アプリケーションには、指定されたペンが必要とする場合、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数または破棄、`CPen`オブジェクトのリソースが使用できないようにします。 アプリケーションでは、デバイス コンテキストで、ペンを選択すると、ペンは削除しないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect

スタイル、幅、および色が指す構造体であるペンを初期化します*lpLogPen*します。

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>パラメーター

*lpLogPen*<br/>
Windows が指す[LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen)ペンについての情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ペンの幅が 1 ピクセルよりも大きい値には、必ず、きは、またはペン スタイルが常に必要です。

ペンにペン スタイルと色が論理カラー テーブルで使用する色に一致しない場合、ペンをディザリングされた色で描画します。 ペンの幅が 1 に等しいまたはそれよりも小さい場合は、ペンのスタイルをきと同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

##  <a name="fromhandle"></a>  CPen::FromHandle

ポインターを返します、 `CPen` Windows GDI pen オブジェクトを識別するハンドルを指定したオブジェクト。

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>パラメーター

*hPen*<br/>
`HPEN` Windows GDI ペンへのハンドルします。

### <a name="return-value"></a>戻り値

ポインター、`CPen`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks


  `CPen` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CPen` オブジェクトが生成され、関連付けられます。 この一時`CPen`すべて一時的なグラフィックを時間があるオブジェクトは削除まで、次回、アプリケーションは、イベント ループでのアイドル時間は、専用、オブジェクトが無効です。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中に無効のみなりました。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

##  <a name="getextlogpen"></a>  CPen::GetExtLogPen

取得、`EXTLOGPEN`構造を基になります。

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*pLogPen*<br/>
指す、[保持](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)ペンについての情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`EXTLOGPEN`構造体、スタイル、幅、およびペンのブラシ属性を定義します。 たとえば、呼び出す`GetExtLogPen`ペンの特定のスタイルに一致するようにします。

ペンの属性については、Windows SDK の次のトピックを参照してください。

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

- [構造体](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>例

次のコード例は、呼び出し元を示します`GetExtLogPen`ペンの属性を取得し、同じ色を持つ新しい、表面的なペンを作成します。

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

##  <a name="getlogpen"></a>  CPen::GetLogPen

取得、`LOGPEN`構造を基になります。

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>パラメーター

*pLogPen*<br/>
指す、 [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)ペンについての情報を格納する構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`LOGPEN`構造体、スタイル、色、およびペンのパターンを定義します。

たとえば、呼び出す`GetLogPen`ペンの特定のスタイルに一致するようにします。

ペンの属性については、Windows SDK の次のトピックを参照してください。

- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)

### <a name="example"></a>例

次のコード例は、呼び出し元を示します`GetLogPen`ペンの文字を取得し、同じ色を持つ新しい solid のペンを作成します。

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

##  <a name="operator_hpen"></a>  CPen::operator HPEN

接続されている Windows GDI ハンドルを取得、`CPen`オブジェクト。

```
operator HPEN() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、Windows GDI オブジェクトを識別するハンドルで表される、`CPen`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子は、キャスト演算子です。

グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](/windows/desktop/gdi/graphic-objects)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>関連項目

[CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CBrush クラス](../../mfc/reference/cbrush-class.md)
