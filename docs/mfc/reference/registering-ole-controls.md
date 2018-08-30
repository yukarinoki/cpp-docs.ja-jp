---
title: OLE コントロールの登録 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4855ca5c461b7437345150f5d199521c48f0b253
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196554"
---
# <a name="registering-ole-controls"></a>OLE コントロールの登録
OLE コントロールは、他の OLE サーバー オブジェクトは、その他の OLE に対応するアプリケーションでアクセスできます。 これは、コントロールのタイプ ライブラリとクラスを登録することによって実現されます。  
  
 次の関数を使用すると、追加し、Windows の登録データベースに、コントロールのクラス、プロパティ ページ、およびタイプ ライブラリを削除できます。  
  
### <a name="registering-ole-controls"></a>OLE コントロールの登録  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|登録情報データベースには、コントロールのクラスを追加します。|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|登録情報データベースには、コントロールのプロパティ ページを追加します。|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|登録情報データベースには、コントロールのタイプ ライブラリを追加します。|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|コントロール クラスまたはプロパティ ページ クラスを登録情報データベースから削除します。|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|登録情報データベースから、コントロールのタイプ ライブラリを削除します。|  
  
 `AfxOleRegisterTypeLib` 通常の制御 DLL の実装で呼び出されます`DllRegisterServer`します。 同様に、`AfxOleUnregisterTypeLib`によって呼び出される`DllUnregisterServer`します。 `AfxOleRegisterControlClass`、 `AfxOleRegisterPropertyPageClass`、および`AfxOleUnregisterClass`によって呼び出される通常の`UpdateRegistry`コントロールのクラス ファクトリやプロパティ ページのメンバー関数。  
  
##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass  
 Windows 登録情報データベースをコントロール クラスを登録します。  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>パラメーター  
 *hInstance*  
 コントロール クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 *clsid*  
 コントロールの一意のクラス ID。  
  
 *pszProgID*  
 コントロールの一意のプログラム ID。  
  
 *idTypeName*  
 コントロールの種類のユーザーが判読できる名前を格納する文字列のリソース ID。  
  
 *idBitmap*  
 OLE コントロールのツールバーまたはパレットを表すために使用するビットマップのリソース ID。  
  
 *nRegFlags*  
 次のフラグの 1 つ以上含まれています。  
  
- `afxRegInsertable` OLE オブジェクトのオブジェクトの挿入 ダイアログ ボックスに表示するには、制御できます。  
  
- `afxRegApartmentThreading` ThreadingModel レジストリ内のスレッド処理モデルの設定アパートメントを = です。  
  
- `afxRegFreeThreading` スレッド処理モデルを ThreadingModel をレジストリに設定する Free を =。  
  
     2 つのフラグを結合する`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both。 参照してください[InprocServer32](/windows/desktop/com/inprocserver32)スレッド モデルの登録の詳細については、Windows SDK に含まれています。  
  
> [!NOTE]
>  4.2、以前のバージョンの MFC で、 **int** *nRegFlags*パラメーターがブール型パラメーター、 *bInsertable*、許可または挿入から挿入されるコントロールを禁止します。オブジェクト ダイアログ ボックス。  
  
 *dwMiscStatus*  
 (Windows SDK に入りますフラグの説明) の次の状態フラグの 1 つ以上含まれています。  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   されて  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 コントロール クラスの一意の ID。  
  
 *wVerMajor*  
 コントロール クラスのメジャー バージョン番号。  
  
 *wVerMinor*  
 コントロール クラスのマイナー バージョン番号。  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 これにより、OLE コントロールの対応するコンテナーで使用されるコントロール。 `AfxOleRegisterControlClass` コントロールの名前と、システム上の場所で、レジストリを更新しもレジストリにコントロールをサポートするスレッド処理モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール"は、と[に関するプロセスとスレッド](/windows/desktop/ProcThread/about-processes-and-threads)Windows SDK にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 上記の例でどのように`AfxOleRegisterControlClass`挿入可能のフラグと呼びますとフラグのアパートメント モデルの 6 番目のパラメーターを作成するための論理和。  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 コントロールが有効なコンテナーでは、オブジェクトの挿入 ダイアログ ボックスに表示されます、アパートメント モデルを認識されます。 完了したら、同じクラスの別のインスタンスが使用を開始する前に 1 つのアパートメントでのコントロールが静的データにアクセスするときに、されていない、スケジューラによって無効にするため、アパートメント モデル対応のコントロールは静的クラスのデータは、ロックで保護を確認する必要があります。同じ静的データ。 クリティカル セクションのコードでは、静的なデータへのアクセスが囲まれます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Windows 登録情報データベースをプロパティ ページ クラスを登録します。  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>パラメーター  
 *hInstance*  
 プロパティ ページ クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 *clsid*  
 プロパティ ページの一意のクラス ID。  
  
 *idTypeName*  
 プロパティ ページのユーザーが判読できる名前を格納する文字列のリソース ID。  
  
 *nRegFlags*  
 フラグを含めることができます。  
  
- `afxRegApartmentThreading` ThreadingModel レジストリ内のスレッド処理モデルの設定アパートメントを = です。  
  
> [!NOTE]
>  MFC 4.2 では、以前のバージョンの MFC で、 **int** *nRegFlags*パラメーターは使用できませんでした。 なお、`afxRegInsertable`フラグ プロパティ ページの有効なオプションではありませんし、設定されている場合に MFC アサートが発生  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 これにより、OLE コントロールの対応するコンテナーで使用されるプロパティ ページができます。 `AfxOleRegisterPropertyPageClass` プロパティ ページの名前と、システム上の場所のレジストリを更新しもレジストリにコントロールをサポートするスレッド処理モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール"は、と[に関するプロセスとスレッド](/windows/desktop/ProcThread/about-processes-and-threads)Windows SDK にします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Windows 登録情報データベースのタイプ ライブラリを登録し、OLE コントロールを認識する他のコンテナーで使用されるタイプ ライブラリを使用します。  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 *hInstance*  
 タイプ ライブラリに関連付けられているアプリケーションのインスタンス ハンドル。  
  
 *tlid*  
 タイプ ライブラリの一意の ID。  
  
 *pszFileName*  
 ローカライズされたタイプ ライブラリの省略可能なファイル名を指す (します。コントロールの TLB) ファイルです。  
  
 *pszHelpDir*  
 タイプ ライブラリのヘルプ ファイルがあるディレクトリの名前。 NULL の場合、ヘルプ ファイルは、タイプ ライブラリ自体と同じディレクトリであると見なされます。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、タイプ ライブラリ名と、システム上の場所で、レジストリを更新します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Windows 登録情報データベースからのコントロールやプロパティ ページ クラスのエントリを削除します。  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>パラメーター  
 *clsID*  
 コントロールまたはプロパティ ページの一意のクラス ID。  
  
 *pszProgID*  
 コントロールまたはプロパティ ページの一意のプログラム ID。  
  
### <a name="return-value"></a>戻り値  
 コントロールまたはプロパティ ページ クラスは正常に登録された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Windows の登録情報データベースからタイプ ライブラリのエントリを削除するには、この関数を呼び出します。  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>パラメーター  
 *tlID*  
 タイプ ライブラリの一意の ID。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが正常に登録できなかった場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
