---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2559b4917f16bb8ddc49b73ace8bda6e1a9bafc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367309"
---
# <a name="cdatapathproperty-class"></a>関数クラス
非同期で読み込める OLE コントロール プロパティを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|関連付けられている非同期 OLE コントロールを取得、`CDataPathProperty`オブジェクト。|  
|[CDataPathProperty::GetPath](#getpath)|プロパティのパス名を取得します。|  
|[CDataPathProperty::Open](#open)|関連付けられた ActiveX (OLE) コントロールの非同期プロパティの読み込みを開始します。|  
|[CDataPathProperty::ResetData](#resetdata)|呼び出し`CAsyncMonikerFile::OnDataAvailable`コントロールのプロパティが変更されたコンテナーに通知します。|  
|[CDataPathProperty::SetControl](#setcontrol)|プロパティに関連付けられた非同期 ActiveX (OLE) コントロールを設定します。|  
|[CDataPathProperty::SetPath](#setpath)|プロパティのパス名を設定します。|  
  
## <a name="remarks"></a>コメント  
 同期の開始後は、非同期のプロパティが読み込まれます。  
  
 クラス`CDataPathProperty`から派生した**CAysncMonikerFile**です。 OLE コントロールの非同期プロパティを実装するには、派生クラスを`CDataPathProperty`、オーバーライドと[OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)です。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次の記事を参照してください。  
  
- [インターネット最初のステップ: ActiveX コントロール](../../mfc/activex-controls-on-the-internet.md)  
  
- [インターネット最初のステップ: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty  
 `CDataPathProperty` オブジェクトを構築します。  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 これに関連する OLE コントロール オブジェクトへのポインター`CDataPathProperty`オブジェクト。  
  
 `lpszPath`  
 可能性のある絶対または相対パス、パスは、プロパティの実際の絶対位置を参照する非同期モニカーの作成に使用します。 `CDataPathProperty` ファイル名の Url を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクトを先頭に付加`file://`パスにします。  
  
### <a name="remarks"></a>コメント  
 `COleControl`によって指されるオブジェクト`pControl`によって使用される**開く**と派生クラスによって取得します。 場合`pControl`は**NULL**で使用されるコントロール**開く**で設定する必要があります`SetControl`です。 場合`lpszPath`は**NULL**、パス経由で渡すことができます**開く**でそれを設定または`SetPath`です。  
  
##  <a name="getcontrol"></a>  CDataPathProperty::GetControl  
 取得するには、このメンバー関数を呼び出す、`COleControl`オブジェクトに関連付けられている、`CDataPathProperty`オブジェクト。  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられている OLE コントロールへのポインターを返します、`CDataPathProperty`オブジェクト。 **NULL**コントロールではなくが関連付けられている場合。  
  
##  <a name="getpath"></a>  CDataPathProperty::GetPath  
 パスを取得、ときに設定するには、このメンバー関数を呼び出す、`CDataPathProperty`オブジェクトが構築、またはで指定された**開く**、または以前の呼び出しで指定された、`SetPath`メンバー関数。  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ自体には、パス名を返します。 パスが指定されていない場合は空にすることができます。  
  
##  <a name="open"></a>  CDataPathProperty::Open  
 関連付けられたコントロールの非同期プロパティの読み込みを開始するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 これに関連する OLE コントロール オブジェクトへのポインター`CDataPathProperty`オブジェクト。  
  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合は、原因に設定されます。  
  
 `lpszPath`  
 可能性のある絶対または相対パス、パスは、プロパティの実際の絶対位置を参照する非同期モニカーの作成に使用します。 `CDataPathProperty` ファイル名の Url を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクトを先頭に付加`file://`パスにします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 取得しようと、関数、`IBindHost`コントロールからのインターフェイスです。  
  
 呼び出しの前に**開く**パスがない場合、プロパティのパスの値を設定する必要があります。 これは、ため、オブジェクトが構築、または呼び出すことによって、`SetPath`メンバー関数。  
  
 呼び出しの前に**開く**コントロールを使用しない (旧称 OLE コントロール) ActiveX コントロールは、オブジェクトに関連付けできます。 これは、ため、オブジェクトが構築、または呼び出すことによって`SetControl`です。  
  
 すべてのオーバー ロード[CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open)はでも`CDataPathProperty`です。  
  
##  <a name="resetdata"></a>  CDataPathProperty::ResetData  
 取得するには、この関数を呼び出す`CAsyncMonikerFile::OnDataAvailable`いるコントロールのプロパティが変更され、非同期的に読み込まれるすべての情報は役に立たなくなったコンテナーに通知します。  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>コメント  
 開始を再起動する必要があります。 派生クラスでは、この関数はそれぞれ異なる既定値をオーバーライドできます。  
  
##  <a name="setcontrol"></a>  CDataPathProperty::SetControl  
 このメンバー関数と非同期の OLE コントロールに関連付ける、`CDataPathProperty`オブジェクト。  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>パラメーター  
 `pControl`  
 プロパティに関連する非同期の OLE コントロールへのポインター。  
  
##  <a name="setpath"></a>  CDataPathProperty::SetPath  
 プロパティのパス名を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPath`  
 パスであり、絶対または相対、プロパティの非同期的に読み込まれている可能性があります。 `CDataPathProperty` ファイル名の Url を使用します。 場合は、`CDataPathProperty`ファイルのオブジェクトを先頭に付加`file://`パスにします。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル イメージ](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
