---
title: COleDispatchDriver クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 57f9eaa33abd0f24a1d584c5ba2a1e4d6f9e5d44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|アタッチ、`IDispatch`への接続、`COleDispatchDriver`オブジェクト。|  
|[Coledispatchdriver::createdispatch](#createdispatch)|作成、`IDispatch`接続にアタッチし、`COleDispatchDriver`オブジェクト。|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|デタッチ、`IDispatch`解放しないまま、接続します。|  
|[ため](#getproperty)|オートメーション プロパティを取得します。|  
|[Coledispatchdriver::invokehelper](#invokehelper)|オートメーション メソッドを呼び出すためのヘルパー。|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|リリース、`IDispatch`接続します。|  
|[このサンプル](#setproperty)|オートメーション プロパティを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|元の値をコピー、`COleDispatchDriver`オブジェクト。|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|基になるアクセス`IDispatch`ポインター。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|解放するかどうかを指定します、`IDispatch`中に`ReleaseDispatch`またはオブジェクトの破棄します。|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|ポインターを示す、`IDispatch`をこのインターフェイスが接続されている`COleDispatchDriver`です。|  
  
## <a name="remarks"></a>コメント  
 `COleDispatchDriver` 基本クラスはありません。  
  
 OLE ディスパッチ インターフェイスは、オブジェクトのメソッドとプロパティへのアクセスを提供します。 メンバー関数は`COleDispatchDriver`アタッチ、デタッチ、作成、およびリリースの種類のディスパッチ接続`IDispatch`です。 他のメンバー関数では、可変個引数リストを使用して、呼び出しを簡略化**idispatch::invoke**です。  
  
 このクラスは、直接使用することができますが、通常は、クラスの追加ウィザードによって作成されたクラスによってのみ使用します。 新しいクラスの派生タイプ ライブラリのインポートによって新しい C++ のクラスを作成するときに`COleDispatchDriver`です。  
  
 使用する方法についての`COleDispatchDriver`、次の記事を参照してください。  
  
- [オートメーション クライアント](../../mfc/automation-clients.md)  
  
- [オートメーション サーバー](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch  
 `AttachDispatch` メンバー関数を呼び出して、 `IDispatch` ポインターを `COleDispatchDriver` オブジェクトにアタッチします。 詳細については、「 [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDispatch`  
 `IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。  
  
 `bAutoRelease`  
 このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
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
 `lpDispatch`  
 `IDispatch` オブジェクトにアタッチされる OLE `COleDispatchDriver` オブジェクトへのポインター。  
  
 `bAutoRelease`  
 このオブジェクトがスコープ外になるときにディスパッチが解放されるかどうかを指定します。  
  
 `dispatchSrc`  
 参照すると、既存`COleDispatchDriver`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 フォーム`COleDispatchDriver`( `LPDISPATCH lpDispatch`、 **BOOL**`bAutoRelease` = **TRUE**) 接続、 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)インターフェイスです。  
  
 フォーム`COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`)、既存のコピー`COleDispatchDriver`オブジェクトおよび参照カウントをインクリメントします。  
  
 フォーム`COleDispatchDriver`に関するページ () を作成、`COleDispatchDriver`オブジェクトしますが、接続していない、`IDispatch`インターフェイスです。 使用する前に`COleDispatchDriver`引数を指定せずに ()、接続してください、`IDispatch`いずれかを使用して[coledispatchdriver::createdispatch](#createdispatch)または[COleDispatchDriver::AttachDispatch](#attachdispatch)です。 詳細については、「 [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)」を参照してください。  
  
### <a name="example"></a>例  
  例を参照して[coledispatchdriver::createdispatch](#createdispatch)です。  
  
##  <a name="createdispatch"></a>  Coledispatchdriver::createdispatch  
 作成、 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)インターフェイス オブジェクトにアタッチし、`COleDispatchDriver`オブジェクト。  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 作成する `IDispatch` 接続オブジェクトのクラス ID。  
  
 `pError`  
 作成の結果ステータス コードを格納する OLE 例外オブジェクトへのポインター。  
  
 `lpszProgID`  
 ディスパッチ オブジェクトが作成されるオートメーション オブジェクトの"Excel.Document.5"などのプログラム ID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch  
 現在の関連付けを解除`IDispatch`このオブジェクトからの接続。  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>戻り値  
 以前接続されている OLE へのポインター`IDispatch`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `IDispatch`は解放されません。  
  
 詳細については、`LPDISPATCH`を入力しを参照してください[IDispatch インターフェイスを実装する](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="getproperty"></a>  ため  
 指定されたオブジェクトのプロパティを取得`dwDispID`です。  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 取得するプロパティを識別します。  
  
 `vtProp`  
 取得するプロパティを指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](#invokehelper)です。  
  
 `pvProp`  
 プロパティの値を受け取る変数のアドレスです。 指定された型に一致する必要があります`vtProp`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="invokehelper"></a>  Coledispatchdriver::invokehelper  
 `dwDispID`によって指定されるコンテキストで `wFlags`によって指定されるオブジェクト メソッドまたはプロパティを呼び出します。  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 呼び出されるメソッドまたはプロパティを識別します。  
  
 `wFlags`  
 **IDispatch::Invoke**呼び出しのコンテキストを記述するフラグ。 である必要があります。 使用可能な値の一覧は、次を参照してください。、`wFlags`パラメーター [idispatch::invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) Windows SDK にします。  
  
 `vtRet`  
 戻り値の型を指定します。 使用可能な値については、「解説」を参照してください。  
  
 `pvRet`  
 プロパティ値または戻り値を受け取る変数のアドレス。 これは、 `vtRet`によって指定される型と一致する必要があります。  
  
 `pbParamInfo`  
 `pbParamInfo`に従うパラメーターの型を指定するバイトの null で終わる文字列へのポインター。  
  
 *...*  
 `pbParamInfo`で指定される型の、パラメーターの変数一覧。  
  
### <a name="remarks"></a>コメント  
 `pbParamInfo` パラメーターは、メソッドまたはプロパティに渡されるパラメーターの型を指定します。 引数の変数一覧は、構文宣言では、 **...** で表されます。  
  
 `vtRet` 引数の指定可能な値は、 `VARENUM` 列挙から取られます。 次の値を指定できます。  
  
|シンボル|戻り値の型|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**バリアント**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `pbParamInfo` 引数は、 **VTS_** 定数のスペース区切りの一覧です。 スペース (コンマではない) で区切られるこれらの値の 1 つ以上は、関数のパラメーター リストを指定します。 使用可能な値が付いて、 [EVENT_CUSTOM](event-maps.md#event_custom)マクロです。  
  
 この関数は、パラメータを **VARIANTARG** 値に変換し、その後、 [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) メソッドを呼び出します。 `Invoke` の呼び出しに失敗すると、この関数は、例外をスローします。 場合、 `SCODE` (状態コード) がによって返される**idispatch::invoke**は`DISP_E_EXCEPTION`、この関数がスローされます、 [COleException](../../mfc/reference/coleexception-class.md)オブジェクトですそれ以外の場合、スロー、 [ 。COleDispatchException](../../mfc/reference/coledispatchexception-class.md)です。  
  
 詳細については、次を参照してください[VARIANTARG](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)、 [IDispatch インターフェイスを実装する](http://msdn.microsoft.com/library/windows/desktop/ms221037\(v=vs.85\).aspx)、 [idispatch::invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx)、および[構造体の COM エラー コード。](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK にします。  
  
### <a name="example"></a>例  
  例を参照して[coledispatchdriver::createdispatch](#createdispatch)です。  
  
##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease  
 場合**TRUE**からアクセスされる COM オブジェクト[m_lpDispatch](#m_lpdispatch)ときに自動的に解放されます[ReleaseDispatch](#releasedispatch)が呼び出されたとき、またはこの`COleDispatchDriver`オブジェクトは破棄されます。  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>コメント  
 既定では、`m_bAutoRelease`に設定されている**TRUE**コンス トラクターでします。  
  
 COM オブジェクトの解放の詳細については、次を参照してください。[参照カウントを実装する](http://msdn.microsoft.com/library/windows/desktop/ms693431)と[iunknown::release](http://msdn.microsoft.com/library/windows/desktop/ms682317) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch  
 ポインター、`IDispatch`をこのインターフェイスが接続されている`COleDispatchDriver`です。  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>コメント  
 `m_lpDispatch`データ メンバーは型のパブリック変数`LPDISPATCH`です。  
  
 詳細については、次を参照してください。 [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[COleDispatchDriver::AttachDispatch](#attachdispatch)です。  
  
##  <a name="operator_eq"></a>  COleDispatchDriver::operator =  
 元の値をコピー、`COleDispatchDriver`オブジェクト。  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispatchSrc`  
 既存へのポインター`COleDispatchDriver`オブジェクト。  
  
##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH  
 基になるアクセス`IDispatch`のポインター、`COleDispatchDriver`オブジェクト。  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch  
 リリース、`IDispatch`接続します。 詳細については、次を参照してください[IDispatch インターフェイスを実装する。](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>コメント  
 この接続の自動リリースが設定されている場合はこの関数呼び出し**IDispatch::Release**インターフェイスを解放する前にします。  
  
### <a name="example"></a>例  
  例を参照して[COleDispatchDriver::AttachDispatch](#attachdispatch)です。  
  
##  <a name="setproperty"></a>  このサンプル  
 `dwDispID`によって指定された OLE オブジェクトのプロパティを設定します。  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDispID`  
 設定するプロパティを識別します。  
  
 `vtProp`  
 設定するプロパティの型を指定します。 使用可能な値は、「解説」セクションを参照して[coledispatchdriver::invokehelper](#invokehelper)です。  
  
 *...*  
 `vtProp`によって指定された型の 1 つのパラメーターです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [MFC サンプル ACDUAL](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
