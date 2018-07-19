---
title: CFont クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a598a05c31c36c7defd5fe2441031d3bccdf20f
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336791"
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
|[CFont::CFont](#cfont)|`CFont` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|初期化します、`CFont`と特性を指定します。|  
|[CFont::CreateFontIndirect](#createfontindirect)|初期化します、`CFont`オブジェクトで指定された特性を持つ、`LOGFONT`構造体。|  
|[CFont::CreatePointFont](#createpointfont)|初期化します、`CFont`指定の高さを持つポイント、および書体 0.1 単位で測定します。|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|同じ`CreateFontIndirect`する点を除いて、フォントの高さは論理ユニットではなく、ポイントの 10 分で測定されます。|  
|[CFont::FromHandle](#fromhandle)|ポインターを返します、 `CFont` Windows HFONT が指定されるとします。|  
|[CFont::GetLogFont](#getlogfont)|入力、`LOGFONT`にアタッチされている論理フォントに関する情報を含む、`CFont`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|アタッチされている Windows GDI フォントのハンドルを返します、`CFont`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 使用する、`CFont`オブジェクト、構築、`CFont`オブジェクトし、を使って Windows フォントをアタッチ[構築](#createfont)、 [CreateFontIndirect](#createfontindirect)、 [CreatePointFont](#createpointfont)、または[CreatePointFontIndirect](#createpointfontindirect)、し、オブジェクトのメンバー関数を使用してフォントを操作します。  
  
 `CreatePointFont`と`CreatePointFontIndirect`関数は、多くの場合より使いやすく`CreateFont`または`CreateFontIndirect`フォントの高さの変換、ポイント サイズから論理ユニットを自動的に行うためです。  
  
 詳細については`CFont`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cfont"></a>  CFont::CFont  
 `CFont` オブジェクトを構築します。  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Remarks  
 結果のオブジェクトを初期化する必要があります`CreateFont`、 `CreateFontIndirect`、 `CreatePointFont`、または`CreatePointFontIndirect`を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>  CFont::CreateFont  
 初期化します、`CFont`指定の特性を持つオブジェクト。  
  
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
 *パラメーター nHeight*  
 フォントの高さを (論理単位) で指定します。 参照してください、`lfHeight`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)説明については、Windows SDK で構造体。 絶対値*パラメーター nHeight*は変換後、16,384 デバイス単位を超えない必要があります。 すべての高さの比較は、すべてのフォントが要求されたサイズを超える場合も、フォント マッパーは要求されたサイズを超えていない最大のフォントまたは最小のフォントを探します。  
  
 *nWidth*  
 フォントで、(論理単位) での平均文字幅を指定します。 場合*nWidth*が 0 の差の絶対値によって決定される最も近い一致を検索する利用可能なフォントの業務に携わる縦横比と一致するデバイスの縦横比場合、。  
  
 *nEscapement*  
 (0.1 度単位) で文字送りベクターと x 軸の表示画面間の角度を指定します。 文字送りベクターは、行の最初と最後の文字のオリジンを行です。 角度は、x 軸から反時計回りに計測されます。 参照してください、`lfEscapement`内のメンバー、`LOGFONT`詳細については、Windows SDK で構造体。  
  
 *nOrientation*  
 (0.1 度単位) を文字のベースラインと x 軸の角度を指定します。 角度は、y 方向のダウンして y 方向が稼働する座標系の x 軸から時計回りに座標系の x 軸から反時計回りに計測されます。  
  
 *nWeight*  
 (1000 ピクセル単位) でのフォントの太さを指定します。 参照してください、 *lfWeight*内のメンバー、`LOGFONT`詳細については、Windows SDK で構造体。 説明の値は概数です。実際の外観はフォントに依存します。 一部のフォントはある FW_NORMAL、FW_REGULAR、および FW_BOLD 重みだけです。 FW_DONTCARE が指定されている場合は、既定の重み付けが使用されます。  
  
 *bItalic*  
 フォントが斜体かどうかを指定します。  
  
 *bUnderline*  
 フォントが下付きかどうかを指定します。  
  
 *cStrikeOut*  
 、フォントの文字を入れるかどうかを指定します。場合、取り消し線フォントを指定します、0 以外の値に設定します。  
  
 *nCharSet*  
 フォントの文字セットを指定します、`lfCharSet`内のメンバー、`LOGFONT`値の一覧については、Windows SDK で構造体。  
  
 OEM 文字セットは、システムによって異なります。  
  
 その他の文字セットでのフォントのシステムに存在する可能性があります。 不明な文字セットとフォントを使用するアプリケーションでは、変換や、そのフォントで表示するのには文字列の解釈がしよう必要があります。 代わりに、文字列を出力するデバイス ドライバーに直接渡す必要があります。  
  
 フォント マッパーでは、DEFAULT_CHARSET 値は使用しません。 アプリケーションでは、名前と完全に記述する論理フォントのフォントのサイズを許可するのに、この値を使用できます。 指定した名前のフォントが存在しない場合、任意の文字セットからのフォントは、指定したフォントの代わりに使用できます。 予期しない結果を避けるためには、アプリケーションは控えめ DEFAULT_CHARSET 値を使用する必要があります。  
  
 *nOutPrecision*  
 目的の出力の有効桁数を指定します。 出力の有効桁数は、要求されたフォントの高さ、幅、文字の方向、傾斜、およびピッチ、出力がどの程度一致する必要がありますを定義します。 参照してください、`lfOutPrecision`内のメンバー、`LOGFONT`と詳細については値の一覧については、Windows SDK で構造体。  
  
 *nClipPrecision*  
 必要なクリッピング精度を指定します。 クリッピング精度は、部分的にクリッピング領域の外側にある文字をクリップする方法を定義します。 参照してください、`lfClipPrecision`内のメンバー、`LOGFONT`値の一覧については、Windows SDK で構造体。  
  
 読み取り専用の埋め込みフォントを使用するには、アプリケーションで使うを指定する必要があります。  
  
 デバイス、truetype フォント、およびベクター フォントの一貫した回転を実現するために、アプリケーションは、OR 演算子を使用して、CLIP_LH_ANGLES 値と組み合わせて、その他の*nClipPrecision*値。 すべてのフォントの回転は、座標系の向きが左手座標系かどうかに依存 CLIP_LH_ANGLES ビットが設定されている場合または右手座標系。 (詳細については、座標系の向きは、の説明を参照して、 *nOrientation*パラメーターです)。CLIP_LH_ANGLES が設定されていない場合は、デバイス フォントは常に、反時計回りに回転しますが、他のフォントの回転は、座標系の向きに依存します。  
  
 *nQuality*  
 実際の物理フォントの論理フォント属性が一致するように、GDI を試みる必要がありますに注意を定義するフォントの出力品質を指定します。 参照してください、`lfQuality`内のメンバー、`LOGFONT`値の一覧については、Windows SDK で構造体。  
  
 *nPitchAndFamily*  
 ピッチとファミリのフォントを指定します。 参照してください、`lfPitchAndFamily`内のメンバー、`LOGFONT`と詳細については値の一覧については、Windows SDK で構造体。  
  
 *lpszFacename*  
 A`CString`またはフォントのタイプフェイス名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619)関数は現在使用可能なすべてのフォントを列挙するために使用できます。 場合*lpszFacename*が null の場合、GDI がデバイスに依存しないタイプフェイスを使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フォントは、任意のデバイス コンテキストのフォントとして後で選択できます。  
  
 `CreateFont`関数は新しい Windows GDI フォントを作成できません。 単に、GDI 使用可能な物理フォントから最も近い一致を選択します。  
  
 アプリケーションは、論理フォントを作成するときに、ほとんどのパラメーターに既定の設定を使用できます。 特定の値を常に指定するパラメーターは、*パラメーター nHeight*と*lpszFacename*します。 場合*パラメーター nHeight*と*lpszFacename*が設定されていないアプリケーションで作成される論理フォントにはデバイスに依存します。  
  
 終了したら、`CFont`によって作成されたオブジェクト、`CreateFont`関数を使用して`CDC::SelectObject`デバイス コンテキストに別のフォントを選択し、削除、`CFont`オブジェクトが不要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect  
 初期化します、`CFont`で指定された特性を持つオブジェクトを[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogFont*  
 指す、`LOGFONT`論理フォントの特性を定義する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フォントは、任意のデバイスの現在のフォントとして後から選択できます。  
  
 このフォントにで指定された特性、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。 使用して、フォントを選択すると、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)メンバー関数は、GDI フォントとマッパーは、既存の物理フォントの論理フォントを一致するようにします。 論理フォントを正確に一致するフォント マッパーに失敗した場合は、要求の特性をできるだけ多く一致する特性を持つ別のフォントを提供します。  
  
 不要になった必要がある場合、`CFont`によって作成されたオブジェクト、`CreateFontIndirect`関数を使用して`CDC::SelectObject`デバイス コンテキストに別のフォントを選択し、削除、`CFont`オブジェクトが不要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>  CFont::CreatePointFont  
 この関数は、指定したタイプフェイスのフォントを作成し、サイズをポイントする簡単な方法を提供します。  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPointSize*  
 10 分の 1 点のフォントの高さを要求します。 (たとえば、渡す 12 ポイントのフォントを指定するのには 120 です。)  
  
 *lpszFaceName*  
 A`CString`またはフォントのタイプフェイス名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows ' EnumFontFamilies 関数は現在使用可能なすべてのフォントを列挙するために使用できます。 場合*lpszFaceName*が null の場合、GDI がデバイスに依存しないタイプフェイスを使用します。  
  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)高さでの変換を使用するオブジェクトを*nPointSize*論理ユニットにします。 NULL の場合は、画面のデバイス コンテキストが、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 高さを自動的に変換します*nPointSize*論理ユニットに CDC オブジェクトを使用して指す*pDC*します。  
  
 終了したら、`CFont`によって作成されたオブジェクト、`CreatePointFont`関数、まず、デバイス コンテキスト外のフォントを選択し、削除、`CFont`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect  
 この関数は、同じ[CreateFontIndirect](#createfontindirect)する点を除いて、`lfHeight`のメンバー、`LOGFONT`は 10 分のデバイスではなく、ポイント単位で解釈されます。  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogFont*  
 指す、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)論理フォントの特性を定義する構造体。 `lfHeight`のメンバー、`LOGFONT`構造は論理ユニットではなく、ポイントの 10 分で測定されます。 (たとえば、設定`lfHeight`を 120 に 12 ポイントのフォントを指定します)。  
  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)高さでの変換を使用するオブジェクトを`lfHeight`論理ユニットにします。 NULL の場合は、画面のデバイス コンテキストが、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、高さを自動的に変換します`lfHeight`論理ユニットに CDC オブジェクトを使用して指す*pDC*渡す前に、`LOGFONT`構造を Windows にログオンします。  
  
 終了したら、`CFont`によって作成されたオブジェクト、`CreatePointFontIndirect`関数、まず、デバイス コンテキスト外のフォントを選択し、削除、`CFont`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CFont::FromHandle  
 ポインターを返します、 `CFont` Windows GDI フォント オブジェクト、HFONT ハンドルが指定されるとします。  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *hFont*  
 Windows フォントに HFONT ハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFont`成功。 それ以外の場合に NULL の場合は、オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 場合、`CFont`ハンドル、一時的にオブジェクトが既にアタッチされていない`CFont`オブジェクトを作成し、接続されています。 この一時`CFont`すべて一時的なグラフィックを時間があるオブジェクトは削除まで、次回、アプリケーションは、イベント ループでのアイドル時間は、専用、オブジェクトが無効です。 言い換えると、別の方法は、一時オブジェクトが 1 つのウィンドウ メッセージを処理中にのみ有効であります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>  CFont::GetLogFont  
 コピーを取得するには、この関数を呼び出して、`LOGFONT`の構造体`CFont`します。  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLogFont*  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)フォント情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、それ以外の場合 0 0 以外の値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>  CFont::operator HFONT  
 アタッチされているフォントの Windows GDI ハンドルを取得するこの演算子を使用して、`CFont`オブジェクト。  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アタッチされている Windows GDI フォント オブジェクトのハンドル`CFont`成功。 それ以外の場合に NULL の場合。  
  
### <a name="remarks"></a>Remarks  
 この演算子は自動的からの変換に使用されるため`CFont`に[フォントとテキスト](http://msdn.microsoft.com/library/windows/desktop/dd144819)、渡すことができます`CFont`HFONTs を期待する関数へのオブジェクト。  
  
 グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



