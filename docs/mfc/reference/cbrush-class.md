---
title: CBrush クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffd5e43267ad6a5a462705f410cc1073161ecf0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954105"
---
# <a name="cbrush-class"></a>CBrush クラス
Windows のグラフィック デバイス インターフェイス (GDI) のブラシをカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|`CBrush` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|スタイル、色、およびで指定されたパターンでブラシを初期化、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|デバイスに依存しないビットマップ (DIB) で指定されたパターンでブラシを初期化します。|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|指定したハッシュ パターンおよび色のブラシを初期化します。|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|ビットマップで指定されたパターンでブラシを初期化します。|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|指定した純色でブラシを初期化します。|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|既定のシステム カラー ブラシを作成します。|  
|[CBrush::FromHandle](#fromhandle)|ポインターを返します、`CBrush`オブジェクト ハンドルを指定して、Windows にとき`HBRUSH`オブジェクト。|  
|[CBrush::GetLogBrush](#getlogbrush)|取得、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CBrush::operator HBRUSH](#operator_hbrush)|接続されている Windows ハンドルを返します、`CBrush`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 使用する、`CBrush`オブジェクトを構築、`CBrush`オブジェクトし、いずれかに渡す`CDC`ブラシを必要とするメンバー関数。  
  
 ブラシは、ハッチ、およびパターン実線、することができます。  
  
 詳細については`CBrush`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cbrush"></a>  CBrush::CBrush  
 `CBrush` オブジェクトを構築します。  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 *crColor*  
 RGB 色としてブラシの前景色を指定します。 ブラシをハッチすると、このパラメーターは、() の陰影の色を指定します。  
  
 *nIndex*  
 ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL` 45 度で下ハッチ (左右から)  
  
- `HS_CROSS` 水平および垂直方向の格子  
  
- `HS_DIAGCROSS` 45 度をクロスハッチします。  
  
- `HS_FDIAGONAL` 45 度の位置 (左右から) 上のハッチ  
  
- `HS_HORIZONTAL` 水平方向の陰影  
  
- `HS_VERTICAL` 垂直方向の陰影  
  
 *pBitmap*  
 指す、`CBitmap`ブラシを描画するビットマップを指定するオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CBrush` 次の 4 つオーバー ロードされたコンス トラクターです。引数なしのコンス トラクターを作成、初期化されていない`CBrush`オブジェクトを使用する前に初期化する必要があります。  
  
 引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CBrush`オブジェクト[CreateSolidBrush](#createsolidbrush)、 [CreateHatchBrush](#createhatchbrush)、 [CreateBrushIndirect](#createbrushindirect)、[とき](#createpatternbrush)、または[構築](#createdibpatternbrush)です。 いずれかの引数を受け取るコンス トラクターを使用する場合、それ以上初期化は必要です。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。  
  
 1 つのコンス トラクター [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)パラメーターが指定した色ソリッド ブラシを構築します。 色の RGB 値を指定およびに構築される、 `RGB` windows マクロです。H.  
  
 2 つのパラメーターを持つコンス トラクターは、ハッチ ブラシを構築します。 *NIndex*ハッチ パターンのインデックスを指定します。 *CrColor*パラメーターは、色を指定します。  
  
 コンス トラクター、`CBitmap`パラメーターは、パターンのブラシを構築します。 パラメーターは、ビットマップを識別します。 使用して作成されたものと見なされます、ビットマップ[CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [cbitmap::createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)です。 塗りつぶしのパターンで使用するビットマップの最小サイズは、8 ピクセルの 8 ピクセルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect  
 スタイル、色、およびで指定されたパターンでブラシを初期化、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogBrush*  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)ブラシについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、任意のデバイス コンテキストの現在のブラシとして後で選択できます。  
  
 (1 平面、1 ビット/ピクセル) にモノクロ ビットマップを使用して作成されたブラシは、現在テキスト色と背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストの色で描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush  
 デバイスに依存しないビットマップ (DIB) で指定されたパターンでブラシを初期化します。  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPackedDIB*  
 パックされたデバイスに依存しないビットマップ (DIB) を含むグローバル メモリ オブジェクトを識別します。  
  
 *nUsage*  
 指定するかどうか、 **bmiColors:operator[]** のフィールド、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) (「パック DIB」の一部) のデータ構造は、明示的な RGB 値またはインデックスを現在実現論理パレットに含まれています。 パラメーターには、値は次のいずれかを指定する必要があります。  
  
- **DIB_PAL_COLORS**カラー テーブルは、16 ビットのインデックスの配列で構成されます。  
  
- **DIB_RGB_COLORS**カラー テーブルには、リテラルの RGB 値が含まれています。  
  
 *lpPackedDIB*  
 成るパックされた DIB が指す、`BITMAPINFO`構造体の直後にビットマップのピクセルを定義するバイト配列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストを選択できます。  
  
 DIB を処理する方法では、2 つのバージョンが異なります。  
  
-   最初のバージョンでは、DIB にハンドルを取得する呼び出しで、Windows`GlobalAlloc`関数をグローバル メモリのブロックを割り当てます。 パックされた DIB にメモリを入力します。  
  
-   2 番目のバージョンで必要はありませんを呼び出す`GlobalAlloc`パックされた DIB のメモリを割り当てられません。  
  
 パックされた DIB から成る、`BITMAPINFO`データ構造体の直後に、ビットマップのピクセルを定義するバイトの配列。 塗りつぶしのパターンとして使用されるビットマップは、8 ピクセル × 8 ピクセルにする必要があります。 ビットマップが大きい場合は、Windows は、最初の 8 行、および 8 列のビットマップの左上隅にあるピクセルに対応するビットのみを使用して、塗りつぶしパターンを作成します。  
  
 選択すると、アプリケーション 2 色 DIB パターン ブラシ モノクロ デバイス コンテキストに、Windows は DIB で指定された色を無視し、代わりに、デバイス コンテキストの現在のテキストと背景色を使用してパターン ブラシを表示します。 DIB の (DIB カラー テーブル内のオフセット 0) にある最初の色にマップされているピクセルは、テキストの色で表示されます。 ピクセル (カラー テーブル内のオフセット 1) にある 2 番目の色にマップの背景色を使用してが表示されます。  
  
 次の Windows 機能の使用については、Windows SDK を参照してください。  
  
- [構築](http://msdn.microsoft.com/library/windows/desktop/dd183492)(3.0 より前のバージョンの Windows 用に記述されたアプリケーションとの互換性のためだけに用意されているこの関数を使用して、`CreateDIBPatternBrushPt`関数です。)。  
  
- [されている](http://msdn.microsoft.com/library/windows/desktop/dd183493)(この関数は、Win32 ベースのアプリケーションで使用する必要があります)。  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush  
 指定したハッシュ パターンおよび色のブラシを初期化します。  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 ブラシの陰影のスタイルを指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL` 45 度で下ハッチ (左右から)  
  
- `HS_CROSS` 水平および垂直方向の格子  
  
- `HS_DIAGCROSS` 45 度をクロスハッチします。  
  
- `HS_FDIAGONAL` 45 度の位置 (左右から) 上のハッチ  
  
- `HS_HORIZONTAL` 水平方向の陰影  
  
- `HS_VERTICAL` 垂直方向の陰影  
  
 *crColor*  
 RGB 色 (の陰影の色) として、ブラシの前景色を指定します。 参照してください[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)詳細については、Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、任意のデバイス コンテキストの現在のブラシとして後で選択できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush  
 ビットマップで指定されたパターンでブラシを初期化します。  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBitmap*  
 ビットマップを識別します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、ラスター オペレーションをサポートする任意のデバイス コンテキストを選択できます。 によって識別されるビットマップ*pBitmap*を使用して初期化は、通常、 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap)、 [cbitmap::createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)、 [CBitmap:。LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap)、または[CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)関数。  
  
 塗りつぶしのパターンとして使用されるビットマップは、8 ピクセル × 8 ピクセルにする必要があります。 ビットマップが大きい場合は、Windows は、最初の 8 行と列のビットマップの左上隅にあるピクセルに対応するビットだけ使用します。  
  
 ブラシ パターンは、関連するビットマップの影響を与えずに削除できます。 これは、任意の数のパターンのブラシを作成するビットマップを使用できることを意味します。  
  
 モノクロ ビットマップ (1 色平面、1 ビット/ピクセル) を使用して作成されたブラシは、現在テキスト色と背景色を使用して描画されます。 0 に設定されたビットで表されるピクセルは、現在のテキストの色で描画されます。 1 に設定されたビットで表されるピクセルは、現在の背景色で描画されます。  
  
 使用方法について[とき](http://msdn.microsoft.com/library/windows/desktop/dd183508)、Windows 機能、Windows SDK を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush  
 指定した純色でブラシを初期化します。  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *crColor*  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)ブラシの色を指定する構造体。 色は、RGB 値を指定し、WINDOWS の RGB マクロに構築されます。H.  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、任意のデバイス コンテキストの現在のブラシとして後で選択できます。  
  
 アプリケーションが完了するとによって作成されたブラシを使用して`CreateSolidBrush`、デバイス コンテキスト外のブラシを選択する必要があります。  
  
### <a name="example"></a>例  
  例を参照して[CBrush::CBrush](#cbrush)です。  
  
##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush  
 ブラシの色を初期化します。  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 色のインデックスを指定します。 この値は、21 ウィンドウ要素のいずれかの描画に使用する色に対応します。 参照してください[GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371)値の一覧については Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 ブラシは、任意のデバイス コンテキストの現在のブラシとして後で選択できます。  
  
 アプリケーションが完了するとによって作成されたブラシを使用して`CreateSysColorBrush`、デバイス コンテキスト外のブラシを選択する必要があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>  CBrush::FromHandle  
 ポインターを返します、`CBrush`オブジェクト ハンドルを指定して、Windows にとき[HBRUSH](#operator_hbrush)オブジェクト。  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *hBrush*  
 `HANDLE` Windows GDI ブラシ。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CBrush`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 場合、`CBrush`オブジェクトが、一時的なハンドルに既にアタッチされていない`CBrush`オブジェクトが作成され、接続されています。 この一時`CBrush`のみ、[次へ]、アプリケーションがまでのアイドル時間イベント ループでオブジェクトが無効です。 この時点では、すべての一時的なグラフィック オブジェクトが削除されます。 つまり、一時オブジェクトは 1 つのウィンドウ メッセージを処理中にのみ有効です。  
  
 グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CBrush::CBrush](#cbrush)です。  
  
##  <a name="getlogbrush"></a>  CBrush::GetLogBrush  
 取得するには、このメンバー関数を呼び出す、`LOGBRUSH`構造体。  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)ブラシについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合と*終了*有効なポインターは、戻り値は、バッファーに格納されるバイト数。  
  
 関数が成功した場合と*終了*は**NULL**、戻り値は、関数の情報を保持するために必要なバイト数にバッファーに保存します。  
  
 関数が失敗した場合、戻り値は 0 です。  
  
### <a name="remarks"></a>Remarks  
 `LOGBRUSH`構造体は、スタイル、色、およびブラシのパターンを定義します。  
  
 たとえば、呼び出す`GetLogBrush`特定の色またはビットマップのパターンに一致します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>  CBrush::operator HBRUSH  
 この演算子のアタッチされた Windows GDI ハンドルの取得を使用して、`CBrush`オブジェクト。  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CBrush`オブジェクト。 それ以外の場合**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 この演算子はキャスト演算子の`HBRUSH`オブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)
