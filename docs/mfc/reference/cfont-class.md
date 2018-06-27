---
title: CFont クラス |Microsoft ドキュメント
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
ms.openlocfilehash: c577a153536b7c9a5def95915e802301841a485b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955028"
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
|[CFont::CreateFont](#createfont)|初期化、`CFont`と特性を指定します。|  
|[CFont::CreateFontIndirect](#createfontindirect)|初期化、`CFont`オブジェクトで指定された特性を持つ、`LOGFONT`構造体。|  
|[CFont::CreatePointFont](#createpointfont)|初期化、`CFont`ポイント、および書体 10 分の 1 単位は、指定された高さでします。|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|同じ`CreateFontIndirect`フォントの高さが論理ユニットではなく、ポイントの 0.1 単位で測定される点が異なります。|  
|[CFont::FromHandle](#fromhandle)|ポインターを返します、 `CFont` Windows が指定されると**HFONT**です。|  
|[CFont::GetLogFont](#getlogfont)|入力、`LOGFONT`にアタッチされている論理フォントに関する情報を含む、`CFont`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|接続されている Windows GDI フォント ハンドルを返します、`CFont`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 使用する、`CFont`オブジェクトを構築、`CFont`オブジェクトし、を使って Windows のフォントをアタッチ[構築](#createfont)、 [CreateFontIndirect](#createfontindirect)、 [CreatePointFont](#createpointfont)、または[CreatePointFontIndirect](#createpointfontindirect)、し、オブジェクトのメンバー関数を使用して、フォントを操作します。  
  
 `CreatePointFont`と`CreatePointFontIndirect`関数は、多くの場合よりも使いやすく`CreateFont`または`CreateFontIndirect`のため、フォントの高さを変換、ポイント サイズから論理ユニットを自動的にします。  
  
 詳細については`CFont`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
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
 結果のオブジェクトを初期化する必要があります`CreateFont`、 `CreateFontIndirect`、 `CreatePointFont`、または`CreatePointFontIndirect`を使用する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>  CFont::CreateFont  
 初期化、`CFont`指定された特性を持つオブジェクト。  
  
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
 フォントの高さ (論理単位) を指定します。 参照してください、`lfHeight`のメンバー、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)詳細については、Windows SDK 内の構造。 絶対値*パラメーター nHeight*が変換されたら、16,384 デバイス単位を超えない必要があります。 高さ比較はすべては、すべてのフォントが要求されたサイズを超える場合も、フォント マッパーは要求されたサイズを超えていない最大のフォントまたは最小のフォントを探します。  
  
 *nWidth*  
 フォントに、平均 (論理単位) で文字幅を指定します。 場合*nWidth*が 0 の使用可能なフォントの差の絶対値によって決定される、最も近い一致を検索するデジタル化縦横比と一致するデバイスの縦横比場合、。  
  
 *nEscapement*  
 角度 (0.1 度単位)、傾斜ベクターと画面の表面の x 軸を指定します。 傾斜ベクターは、行の最初と最後の文字の原点を結ぶ直線です。 角度は、x 軸から反時計回りに計測されます。 参照してください、`lfEscapement`内のメンバー、`LOGFONT`詳細については、Windows SDK 内の構造。  
  
 *nOrientation*  
 角度 (0.1 度単位) を文字のベースラインと x 軸を指定します。 角度は、y 軸方向のダウンして、x 軸の y 方向が上の座標系から時計回りに座標系の x 軸から反時計回りに計測されます。  
  
 *nWeight*  
 インク付きピクセルあたり 1000 単位のフォントの太さを指定します。 参照してください、 *lfWeight*内のメンバー、`LOGFONT`詳細については、Windows SDK 内の構造。 値は概算です。実際の外観はフォントに依存します。 一部のフォントがのみがある`FW_NORMAL`、 `FW_REGULAR`、および`FW_BOLD`重み。 場合`FW_DONTCARE`を指定すると、既定の重みを使用します。  
  
 *bItalic*  
 フォントが斜体かどうかを指定します。  
  
 *bUnderline*  
 フォントに下線が引かれているかどうかを指定します。  
  
 *cStrikeOut*  
 フォントの文字は、取り消しかどうかを指定します。場合に取り消し線フォントを指定する 0 以外の値に設定します。  
  
 *nCharSet*  
 フォントの文字セットを指定します、`lfCharSet`内のメンバー、`LOGFONT`値の一覧については、Windows SDK 内の構造。  
  
 OEM 文字セットは、システムによって異なります。  
  
 その他の文字セットを使用するフォント システムに存在する可能性があります。 不明な文字セットとフォントを使用するアプリケーションは、変換や、そのフォントで表示するのには、文字列の解釈しないでください。 代わりに、文字列は、出力デバイス ドライバーに直接渡されます。  
  
 フォント マッパーが使用しない、`DEFAULT_CHARSET`値。 アプリケーションは、この値を使用した論理フォントを完全に記述するのにフォントのサイズと名前を許可します。 指定した名前のフォントが存在しない場合、指定されたフォントの任意の文字セットからフォントに置き換えられることができます。 予期しない結果を避けるためには、アプリケーションを使用する必要があります、`DEFAULT_CHARSET`値の限定的に使用します。  
  
 *nOutPrecision*  
 目的の出力の有効桁数を指定します。 出力の精度は、要求されたフォントの高さ、幅、文字の方向、傾斜、およびピッチに出力をどの程度一致する必要がありますを定義します。 参照してください、`lfOutPrecision`内のメンバー、`LOGFONT`値および詳細の一覧については、Windows SDK 内の構造。  
  
 *nClipPrecision*  
 必要な領域の有効桁数を指定します。 クリッピング精度は、部分的にクリッピング領域の外側にある文字をクリップする方法を定義します。 参照してください、`lfClipPrecision`内のメンバー、`LOGFONT`値の一覧については、Windows SDK 内の構造。  
  
 読み取り専用の埋め込みフォントを使用するアプリケーションを指定する必要があります`CLIP_ENCAPSULATE`です。  
  
 デバイス、truetype フォント、およびベクター フォントの一貫した回転を実現するために、アプリケーションは、OR 演算子を使用して、結合、`CLIP_LH_ANGLES`値とその他の*nClipPrecision*値。 場合、`CLIP_LH_ANGLES`ビットが設定されている、すべてのフォントの回転は、座標系の向きが左ききかどうかによって異なりますか右回りです。 (座標系の方向に関する詳細については、の説明を参照して、 *nOrientation*パラメーターです)。場合`CLIP_LH_ANGLES`が設定されていないデバイス フォントを常に反時計回りに回転、その他のフォントの回転、座標系の向きに依存します。  
  
 *nQuality*  
 実際の物理的なフォントの論理フォント属性と一致する GDI を試みる必要がありますに注意を定義するフォントの出力の品質を指定します。 参照してください、`lfQuality`内のメンバー、`LOGFONT`値の一覧については、Windows SDK 内の構造。  
  
 *nPitchAndFamily*  
 ピッチとファミリのフォントを指定します。 参照してください、`lfPitchAndFamily`内のメンバー、`LOGFONT`値および詳細の一覧については、Windows SDK 内の構造。  
  
 *lpszFacename*  
 A`CString`またはフォントのフォント名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619)現在使用可能なすべてのフォントを列挙する関数を使用できます。 場合*lpszFacename*は`NULL`GDI がデバイスに依存しない書体を使用します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フォントは、任意のデバイス コンテキストのフォントとして後で選択できます。  
  
 `CreateFont`関数は新しい Windows GDI フォントは作成されません。 単からを選択、最も近い利用できる物理フォント GDI にします。  
  
 アプリケーションは、論理フォントを作成するときに、ほとんどのパラメーターに既定の設定を使用できます。 特定の値を指定する必要がありますは常に、パラメーターが*パラメーター nHeight*と*lpszFacename*です。 場合*パラメーター nHeight*と*lpszFacename*が設定されていないアプリケーションで作成される論理フォントがデバイスに依存します。  
  
 使用が終了したら、`CFont`によって作成されたオブジェクト、`CreateFont`関数を使用して`CDC::SelectObject`をデバイス コンテキストに、別のフォントを選択し、削除、`CFont`不要になったオブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect  
 初期化、`CFont`オブジェクトで指定された特性を持つ、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogFont*  
 指す、`LOGFONT`論理フォントの特性を定義する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フォントは、任意のデバイスの現在のフォントとして後で選択できます。  
  
 このフォントがで指定された特性を持つ、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)構造体。 使用して、フォントを選択すると、 [cdc::selectobject](../../mfc/reference/cdc-class.md#selectobject)メンバー関数は、GDI フォント マッパーを既存の物理フォントの論理フォントを一致させようとします。 論理フォントを正確に一致するフォント マッパーに失敗した場合、代替のフォントとして可能な要求の特性の多くを提供します。  
  
 不要になった必要がある場合、`CFont`によって作成されたオブジェクト、`CreateFontIndirect`関数を使用して`CDC::SelectObject`をデバイス コンテキストに、別のフォントを選択し、削除、`CFont`不要になったオブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>  CFont::CreatePointFont  
 この関数は、指定したフォントのフォントを作成し、ポイント サイズを簡単な方法を提供します。  
  
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
 A`CString`またはフォントのフォント名を指定する null で終わる文字列へのポインター。 この文字列の長さは 30 文字を超えない必要があります。 Windows **EnumFontFamilies**現在使用可能なすべてのフォントを列挙する関数を使用できます。 場合*lpszFaceName*は**NULL**GDI がデバイスに依存しない書体を使用します。  
  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)高さでの変換に使用するオブジェクト*nPointSize*論理ユニットにします。 場合**NULL**画面のデバイス コンテキストは、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 高さを自動的に変換*nPointSize*を使用して論理ユニットに、`CDC`によって指されるオブジェクト*pDC*です。  
  
 使用が終了したら、`CFont`によって作成されたオブジェクト、`CreatePointFont`関数の最初に、デバイス コンテキスト外のフォントを選択し、削除、`CFont`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect  
 この関数は、同じ[CreateFontIndirect](#createfontindirect)する点を除いて、**する**のメンバー、`LOGFONT`はデバイスではなく、ポイント単位の部分の 1/10 に解釈されます。  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpLogFont*  
 指す、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)論理フォントの特性を定義する構造体。 **する**のメンバー、`LOGFONT`構造は論理ユニットではなく、ポイントの 0.1 単位で測定されます。 (たとえば、設定**する**を 120 に 12 ポイントのフォント)。  
  
 *pDC*  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)高さでの変換に使用するオブジェクト**する**論理ユニットにします。 場合**NULL**画面のデバイス コンテキストは、変換に使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、高さで自動的に変換します。**する**を使用して論理ユニットに、`CDC`によって指されるオブジェクト*pDC*渡す前に、`LOGFONT`構造 Windows にログオンします。  
  
 使用が終了したら、`CFont`によって作成されたオブジェクト、`CreatePointFontIndirect`関数の最初に、デバイス コンテキスト外のフォントを選択し、削除、`CFont`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CFont::FromHandle  
 ポインターを返します、`CFont`が指定されると、 **HFONT** Windows GDI フォント オブジェクトへのハンドルします。  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *hFont*  
 **HFONT** Windows フォントを処理します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFont`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 場合、`CFont`オブジェクトが、一時的なハンドルに既にアタッチされていない`CFont`オブジェクトが作成され、接続されています。 この一時`CFont`オブジェクトが有効では、次回アプリケーションがある移動するまでのアイドル時間イベント ループで、すべて一時的なグラフィックを時間でオブジェクトが削除専用です。 言い換えるとは、一時オブジェクトが 1 つのウィンドウ メッセージを処理中にのみ有効であります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>  CFont::GetLogFont  
 コピーを取得するには、この関数を呼び出して、`LOGFONT`の構造体`CFont`です。  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLogFont*  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)フォント情報を受け取る構造です。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、それ以外の場合 0 0 以外の値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>  CFont::operator HFONT  
 この演算子にアタッチされているフォントの Windows GDI ハンドルの取得を使用して、`CFont`オブジェクト。  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>戻り値  
 接続されている Windows GDI フォント オブジェクトのハンドル`CFont`成功した場合は**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 この演算子は自動的に使用からの変換のため`CFont`に[フォントとテキスト](http://msdn.microsoft.com/library/windows/desktop/dd144819)を渡すことができます`CFont`する関数にオブジェクト**HFONT**s。  
  
 グラフィック オブジェクトの使用に関する詳細については、次を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



