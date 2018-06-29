---
title: CPen クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17337239a3a58a0283fc96eadcd4417c3d5c69b0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079591"
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
|[CPen::CreatePen](#createpen)|指定したスタイル、幅、およびブラシ属性と論理表面的なまたは幾何学的ペンを作成しにアタッチ、`CPen`オブジェクト。|  
|[CPen::CreatePenIndirect](#createpenindirect)|スタイル、幅、および色でペンを作成、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)構造、およびそれにアタッチ、`CPen`オブジェクト。|  
|[CPen::FromHandle](#fromhandle)|ポインターを返します、 `CPen` Windows が指定されると`HPEN`です。|  
|[CPen::GetExtLogPen](#getextlogpen)|取得、[保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)構造体の基になります。|  
|[CPen::GetLogPen](#getlogpen)|取得、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)構造体の基になります。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|接続されている Windows ハンドルを返します、`CPen`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 使用する方法についての`CPen`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
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
 *nPenStyle*  
 ペンのスタイルを指定します。 コンス トラクターの最初のバージョンで、このパラメーターには、次の値のいずれかを指定できます。  
  
- **きは**ソリッド ペンを作成します。  
  
- **PS_DASH**破線のペンを作成します。 ペンの幅が 1 または少ない、デバイスでの単位である場合にのみ有効です。  
  
- **PS_DOT**点線ペンを作成します。 ペンの幅が 1 または少ない、デバイスでの単位である場合にのみ有効です。  
  
- **PS_DASHDOT**の代替ダッシュとのドットでペンを作成します。 ペンの幅が 1 または少ない、デバイスでの単位である場合にのみ有効です。  
  
- **PS_DASHDOTDOT**の代替ダッシュと 2 つのドットでペンを作成します。 ペンの幅が 1 または少ない、デバイスでの単位である場合にのみ有効です。  
  
- **必ず**null ペンを作成します。  
  
- **ペン**外接する四角形を指定する Windows GDI 出力関数によって生成される閉じた図形のフレーム内の行を描画するペンを作成 (たとえば、 `Ellipse`、 `Rectangle`、 `RoundRect`、 `Pie`、`Chord`メンバー関数)。 外接する四角形が指定されていない Windows GDI 関数と共にこのスタイルを使用した場合 (たとえば、`LineTo`メンバー関数)、ペンの描画領域は、フレームによって制限を受けません。  
  
 2 番目のバージョン、`CPen`コンス トラクターは、種類、スタイル、端点キャップ、および結合の属性の組み合わせを指定します。 ビットごとの OR 演算子を使用して、各カテゴリの値を組み合わせる必要があります (&#124;)。 ペンの種類には、次の値のいずれかを指定できます。  
  
- **PS_GEOMETRIC**幾何学的ペンを作成します。  
  
- **PS_COSMETIC**表面的なペンを作成します。  
  
     2 番目のバージョン、`CPen`コンス トラクターを次のペンのスタイルを追加する*nPenStyle*:  
  
- **PS_ALTERNATE**他のすべてのピクセルを設定するペンを作成します。 (このスタイルは、表面的なペンにのみ適用)。  
  
- **PS_USERSTYLE**ユーザーが指定したスタイルの配列を使用するペンを作成します。  
  
     端点キャップには、次の値のいずれかを指定できます。  
  
- **PS_ENDCAP_ROUND**端点キャップ、round です。  
  
- **PS_ENDCAP_SQUARE**端点キャップが四角形。  
  
- **PS_ENDCAP_FLAT**端点キャップがフラットです。  
  
     結合には、次の値のいずれかを指定できます。  
  
- **PS_JOIN_BEVEL**斜め結合します。  
  
- **PS_JOIN_MITER**結合はマイターによって設定された現在の制限内にあるときに、 [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076)関数。 結合は、この制限を超えている場合に、斜めになります。  
  
- **PS_JOIN_ROUND**結合は round です。  
  
 *nWidth*  
 ペンの幅を指定します。  
  
-   コンス トラクターの最初のバージョンの場合、この値は 0、デバイス単位の幅は常にマッピング モードに関係なく、1 ピクセルです。  
  
-   コンス トラクターの 2 番目のバージョンの場合は*nPenStyle*は**PS_GEOMETRIC**幅は、論理単位で指定します。 場合*nPenStyle*は**PS_COSMETIC**幅が 1 に設定する必要があります。  
  
 *crColor*  
 ペンの RGB 色が含まれています。  
  
 *終了*  
 指す、`LOGBRUSH`構造体。 場合*nPenStyle*は**PS_COSMETIC**、 *lbColor*のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、 *lbStyle*のメンバー、`LOGBRUSH`に構造を設定する必要があります**BS_SOLID**です。 場合*nPenStyle*は**PS_GEOMETRIC**、すべてのメンバーは、ペンのブラシ属性を指定するために使用する必要があります。  
  
 *nStyleCount*  
 長さをダブルワード単位を指定、 *lpStyle*配列。 この値が場合は 0 にする必要があります*nPenStyle*は**PS_USERSTYLE**です。  
  
 *lpStyle*  
 ダブルワードの値の配列を指します。 最初の値では、最初のダッシュの長さを指定したユーザー定義のスタイル、2 番目の値は、最初のスペースの長さを指定します。 このポインターがある必要があります**NULL**場合*nPenStyle*は**PS_USERSTYLE**です。  
  
### <a name="remarks"></a>Remarks  
 引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CPen`オブジェクトを`CreatePen`、 `CreatePenIndirect`、または`CreateStockObject`メンバー関数。  
  
 引数を受け取るコンス トラクターを使用する場合は、さらに初期化もする必要はありません。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>  CPen::CreatePen  
 指定したスタイル、幅、およびブラシ属性と論理表面的なまたは幾何学的ペンを作成しにアタッチ、`CPen`オブジェクト。  
  
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
 *nPenStyle*  
 ペンのスタイルを指定します。 使用可能な値の一覧は、次を参照してください。、 *nPenStyle*内のパラメーター、 [CPen](#cpen)コンス トラクターです。  
  
 *nWidth*  
 ペンの幅を指定します。  
  
-   最初のバージョンの`CreatePen`、デバイス単位の幅がマッピング モードに関係なく、1 ピクセルでは常にこの値が 0 の場合。  
  
-   2 番目のバージョンの`CreatePen`場合は、 *nPenStyle*は**PS_GEOMETRIC**幅は、論理単位で指定します。 場合*nPenStyle*は**PS_COSMETIC**幅が 1 に設定する必要があります。  
  
 *crColor*  
 ペンの RGB 色が含まれています。  
  
 *終了*  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。 場合*nPenStyle*は**PS_COSMETIC**、 **lbColor**のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、 *lbStyle*のメンバー、`LOGBRUSH`に構造を設定する必要があります**BS_SOLID**です。 場合**nPenStyle**は**PS_GEOMETRIC**、すべてのメンバーは、ペンのブラシ属性を指定するために使用する必要があります。  
  
 *nStyleCount*  
 長さをダブルワード単位を指定、 *lpStyle*配列。 この値が場合は 0 にする必要があります*nPenStyle*は**PS_USERSTYLE**です。  
  
 *lpStyle*  
 ダブルワードの値の配列を指します。 最初の値では、最初のダッシュの長さを指定したユーザー定義のスタイル、2 番目の値は、最初のスペースの長さを指定します。 このポインターがある必要があります**NULL**場合*nPenStyle*は**PS_USERSTYLE**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外のメソッドが失敗した場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 最初のバージョンの`CreatePen`指定したスタイル、幅、および色のペンを初期化します。 任意のデバイス コンテキストの現在のペンとペンを後で選択できます。  
  
 ペンの幅を超える 1 ピクセルは常にいずれか、**必ず**、**きは**、または**ペン**スタイル。  
  
 ペンがある場合、**ペン**スタイルと色が論理カラー テーブルで使用する色に一致しない、ペンをディザリングされた色で描画します。 **きは**をディザリングされた色でペンを作成するのには、ペンのスタイルを使用できません。 スタイル**ペン**と同じ**きは**ペンの幅が 1 未満の場合。  
  
 2 番目のバージョンの`CreatePen`論理表面的なまたは幾何学的ペン、指定されたスタイル、幅、およびブラシ属性を初期化します。 表面的なペンの幅は、常に 1 になります。幾何学模様のペンの幅は常に、ワールド単位で指定します。 アプリケーションには、論理ペンが作成されたら、それを選択できますそのペン デバイス コンテキストに呼び出すことによって、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)関数。 デバイス コンテキストにペンを選択すると後、は、直線と曲線の描画に使用できます。  
  
-   場合*nPenStyle*は**PS_COSMETIC**と**PS_USERSTYLE**、内のエントリ、 *lpStyle*配列ダッシュと空白での長さを指定します。スタイルの単位です。 スタイル、単位は、直線を描画するペンを使用しているデバイスによって定義されます。  
  
-   場合*nPenStyle*は**PS_GEOMETRIC**と**PS_USERSTYLE**、内のエントリ、 *lpStyle*配列ダッシュと空白での長さを指定します。論理ユニット。  
  
-   場合*nPenStyle*は**PS_ALTERNATE**スタイル、単位は無視され、他のすべてのピクセルを設定します。  
  
 呼び出して、アプリケーションには、特定のペン不要になったが必要な場合、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数または破壊、`CPen`オブジェクトのリソースが使用できないようにします。 デバイス コンテキストでペンを選択すると、アプリケーションは、ペンを削除しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect  
 ペンをスタイル、幅、およびが指す構造体で指定された色を初期化します*lpLogPen*です。  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogPen*  
 Windows が指す[LOGPEN](../../mfc/reference/logpen-structure.md)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ペンの幅を超える 1 ピクセルは常にいずれか、**必ず**、**きは**、または**ペン**スタイル。  
  
 ペンがある場合、**ペン**スタイルと色が論理カラー テーブルで使用する色に一致しない、ペンをディザリングされた色で描画します。 **ペン**スタイルは**きは**ペンの幅が 1 未満の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>  CPen::FromHandle  
 ポインターを返します、 `CPen` Windows GDI pen オブジェクトへのハンドルを指定されたオブジェクト。  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPen*  
 `HPEN` Windows GDI ペンへのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPen`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 `CPen` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CPen` オブジェクトが生成され、関連付けられます。 この一時`CPen`オブジェクトが有効では、次回アプリケーションがある移動するまでのアイドル時間イベント ループで、すべて一時的なグラフィックを時間でオブジェクトが削除専用です。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中に有効なのみなりました。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>  CPen::GetExtLogPen  
 取得、**保持**構造体の基になります。  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLogPen*  
 指す、[保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 **保持**構造体は、スタイル、幅、およびペンのブラシの属性を定義します。 たとえば、呼び出す`GetExtLogPen`ペンの特定のスタイルを一致するようにします。  
  
 ペンの属性については、Windows SDK では、次のトピックを参照してください。  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [構造体](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>例  
 次のコード例に示します通話`GetExtLogPen`ペンの属性を取得し、同じ色を持つ新しい表面的なペンを作成します。  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>  CPen::GetLogPen  
 取得、`LOGPEN`構造体の基になります。  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLogPen*  
 指す、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `LOGPEN`構造体は、スタイル、色、およびペンのパターンを定義します。  
  
 たとえば、呼び出す`GetLogPen`ペンの特定のスタイルを一致するようにします。  
  
 ペンの属性については、Windows SDK では、次のトピックを参照してください。  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>例  
 次のコード例に示します通話`GetLogPen`ペンの文字を取得し、同じ色を持つ新しい実線のペンを作成します。  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>  CPen::operator HPEN  
 接続されている Windows GDI ハンドルを取得、`CPen`オブジェクト。  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CPen`オブジェクト。 それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 この演算子はキャスト演算子の`HPEN`オブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、記事を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)
