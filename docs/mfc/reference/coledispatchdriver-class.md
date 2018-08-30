---
title: COleDispatchDriver クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e25684e0adcace0510f74bdc98968ef52ad6d797
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209569"
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver クラス
OLE オートメーションのクライアント側を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDispatchDriver  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|`COleDispatchDriver` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|アタッチする`IDispatch`への接続、`COleDispatchDriver`オブジェクト。|  
|[Coledispatchdriver::createdispatch](#createdispatch)|作成、`IDispatch`接続にアタッチします、`COleDispatchDriver`オブジェクト。|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|デタッチ、`IDispatch`解放しないまま、接続します。|  
|[ため](#getproperty)|オートメーション プロパティを取得します。|  
|[Coledispatchdriver::invokehelper](#invokehelper)|オートメーション メソッドを呼び出すためのヘルパーです。|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|リリース、`IDispatch`接続します。|  
|[このサンプル](#setproperty)|オートメーション プロパティを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|コピー元の値に、`COleDispatchDriver`オブジェクト。|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|基になるにアクセスする`IDispatch`ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|解放するかどうかを指定します、`IDispatch`中に`ReleaseDispatch`またはオブジェクトの破棄。|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|ポインターを示します、`IDispatch`このインターフェイスがアタッチされている`COleDispatchDriver`します。|  
  
## <a name="remarks"></a>Remarks  
 `COleDispatchDriver` 基本クラスはありません。  
  
 OLE ディスパッチ インターフェイスでは、オブジェクトのメソッドとプロパティへのアクセスを提供します。 メンバー関数の`COleDispatchDriver`アタッチ、デタッチ、作成、およびリリースの種類のディスパッチ接続`IDispatch`します。 その他のメンバー関数では、可変個引数リストを使用して、呼び出しを簡略化`IDispatch::Invoke`します。  
  
 このクラスは、直接使用することができますが、通常はクラスの追加ウィザードによって作成されたクラスのみで使用します。 新しいクラスの派生タイプ ライブラリをインポートすることで新しい C++ クラスを作成するときに`COleDispatchDriver`します。  
  
 使用しての詳細については`COleDispatchDriver`、次の記事を参照してください。  
  
- [オートメーション クライアント](../../mfc/automation-clients.md)  
  
- [オートメーション サーバー](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch  
 `AttachDispatch` メンバー関数を呼び出して、 `IDispatch` ポインターを `COleDispatchDriver` オブジェクトにアタッチします。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDispatch*  
 `IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。  
  
 *bAutoRelease*  
 このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、 `IDispatch` オブジェクトに既にアタッチされている `COleDispatchDriver` ポインターを解放します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]  
  
##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver  
 `COleDispatchDriver` オブジェクトを構築します。  
  
```  
COleDispatchDriver();  
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);  
  COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDispatch*  
 `IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。  
  
 *bAutoRelease*  
 このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。  
  
 *dispatchSrc*  
 参照すると、既存`COleDispatchDriver`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 フォーム`COleDispatchDriver`( `LPDISPATCH lpDispatch`、 **BOOL**`bAutoRelease` = **TRUE**) 接続、 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)インターフェイス。  
  
 フォーム`COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`)、既存のコピー`COleDispatchDriver`オブジェクトし、参照カウントをインクリメントします。  
  
 フォーム`COleDispatchDriver`() を作成、`COleDispatchDriver`オブジェクトしますが、接続していない、`IDispatch`インターフェイス。 使用する前に`COleDispatchDriver`接続する必要があります (引数なし)、`IDispatch`をいずれかを使用して[coledispatchdriver::createdispatch](#createdispatch)または[COleDispatchDriver::AttachDispatch](#attachdispatch)します。 詳細については、「 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)」を参照してください。  
  
### <a name="example"></a>例  
  例をご覧ください[coledispatchdriver::createdispatch](#createdispatch)します。  
  
##  <a name="createdispatch"></a>  Coledispatchdriver::createdispatch  
 作成、 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)インターフェイス オブジェクトにアタッチします、`COleDispatchDriver`オブジェクト。  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *clsid*  
 作成する `IDispatch` 接続オブジェクトのクラス ID。  
  
 *pError*  
 作成の結果ステータス コードを格納する OLE 例外オブジェクトへのポインター。  
  
 *lpszProgID*  
 ディスパッチ オブジェクトが作成されるオートメーション オブジェクトの"Excel.Document.5"などのプログラム ID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch  
 現在のデタッチ`IDispatch`このオブジェクトからの接続。  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>戻り値  
 以前に接続されている OLE へのポインター`IDispatch`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `IDispatch`は解放されません。  
  
 LPDISPATCH 型の詳細については、次を参照してください。 [IDispatch インターフェイスを実装する](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="getproperty"></a>  ため  
 指定されたオブジェクトのプロパティを取得*dwDispID*します。  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 取得するプロパティを識別します。  
  
 *vtProp*  
 取得するプロパティを指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](#invokehelper)します。  
  
 *pvProp*  
 プロパティの値を受け取る変数のアドレス。 指定された型に一致する必要があります*vtProp*します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="invokehelper"></a>  Coledispatchdriver::invokehelper  
 オブジェクトのメソッドまたはプロパティで指定された呼び出し*dwDispID*で指定されたコンテキストで*wFlags*します。  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 呼び出されるメソッドまたはプロパティを識別します。  
  
 *wflags が*  
 呼び出しのコンテキストを記述するフラグ`IDispatch::Invoke`します。 . 使用可能な値の一覧は、次を参照してください。、 *wFlags*パラメーター [idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK にします。  
  
 *変数*  
 戻り値の型を指定します。 使用可能な値については、「解説」を参照してください。  
  
 *pvRet*  
 プロパティ値または戻り値を受け取る変数のアドレス。 指定された型に一致する必要があります*変数*します。  
  
 *pbParamInfo*  
 次のパラメーターの型を指定するバイトの null で終わる文字列へのポインター *pbParamInfo*します。  
  
 *...*  
 パラメーターで指定された型の変数一覧*pbParamInfo*します。  
  
### <a name="remarks"></a>Remarks  
 *PbParamInfo*パラメーターがメソッドまたはプロパティに渡されるパラメーターの型を指定します。 引数の変数一覧は、構文宣言では、 **...** で表されます。  
  
 指定できる値、*変数*引数は、の VARENUM 列挙から取得されます。 次の値を指定できます。  
  
|シンボル|戻り値の型|  
|------------|-----------------|  
|VT_EMPTY|**void**|  
|VT_I2|**short**|  
|VT_I4|**long**|  
|VT_R4|**float**|  
|VT_R8|**double**|  
|VT_CY|**CY**|  
|VT_DATE|**DATE**|  
|VT_BSTR|BSTR|  
|VT_DISPATCH|LPDISPATCH|  
|VT_ERROR|SCODE|  
|VT_BOOL|**BOOL**|  
|VT_VARIANT|**バリアント**|  
|VT_UNKNOWN|LPUNKNOWN|  
  
 *PbParamInfo*引数は、スペースで区切られたリストの**vts _** 定数。 スペース (コンマではない) で区切られるこれらの値の 1 つ以上は、関数のパラメーター リストを指定します。 使用可能な値が付いて、 [EVENT_CUSTOM](event-maps.md#event_custom)マクロ。  
  
 この関数は VARIANTARG 値にパラメーターを変換し、呼び出す、 [idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)メソッド。 `Invoke` の呼び出しに失敗すると、この関数は、例外をスローします。 SCODE (状態コード) がによって返される場合`IDispatch::Invoke`DISP_E_EXCEPTION は、この関数がスローされます、 [COleException](../../mfc/reference/coleexception-class.md)オブジェクト。 それ以外の場合、スロー、 [COleDispatchException](../../mfc/reference/coledispatchexception-class.md)。  
  
 詳細については、次を参照してください[VARIANTARG](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)、 [IDispatch インターフェイスを実装する](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)、 [idispatch::invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)、および[COM エラー コードの構造。](/windows/desktop/com/structure-of-com-error-codes) Windows SDK にします。  
  
### <a name="example"></a>例  
  例をご覧ください[coledispatchdriver::createdispatch](#createdispatch)します。  
  
##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease  
 TRUE の場合、COM オブジェクト アクセス[m_lpDispatch](#m_lpdispatch)ときに自動的に解放されます[ReleaseDispatch](#releasedispatch)が呼び出されますとき、またはこの`COleDispatchDriver`オブジェクトは破棄されます。  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>Remarks  
 既定では、`m_bAutoRelease`コンス トラクターで TRUE に設定します。  
  
 COM オブジェクトの解放の詳細については、次を参照してください。[参照カウントを実装する](/windows/desktop/com/implementing-reference-counting)と[:release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch  
 ポインター、`IDispatch`このインターフェイスがアタッチされている`COleDispatchDriver`します。  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_lpDispatch`データ メンバーが型 LPDISPATCH のパブリック変数です。  
  
 詳細については、次を参照してください。 [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例をご覧ください[COleDispatchDriver::AttachDispatch](#attachdispatch)します。  
  
##  <a name="operator_eq"></a>  COleDispatchDriver::operator =  
 コピー元の値に、`COleDispatchDriver`オブジェクト。  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispatchSrc*  
 既存へのポインター`COleDispatchDriver`オブジェクト。  
  
##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH  
 基になるにアクセスする`IDispatch`のポインター、`COleDispatchDriver`オブジェクト。  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch  
 リリース、`IDispatch`接続します。 詳細については、次を参照してください[IDispatch インターフェイスを実装する。](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>Remarks  
 この接続の自動リリースが設定されている場合はこの関数呼び出し`IDispatch::Release`インターフェイスを解放する前にします。  
  
### <a name="example"></a>例  
  例をご覧ください[COleDispatchDriver::AttachDispatch](#attachdispatch)します。  
  
##  <a name="setproperty"></a>  このサンプル  
 指定した OLE オブジェクトのプロパティを設定*dwDispID*します。  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDispID*  
 設定するプロパティを識別します。  
  
 *vtProp*  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」を参照してください。 [coledispatchdriver::invokehelper](#invokehelper)します。  
  
 *...*  
 1 つのパラメーターで指定された型の*vtProp*します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [MFC サンプル ACDUAL](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
