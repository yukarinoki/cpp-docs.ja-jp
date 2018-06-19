---
title: OLE コントロールの登録 |Microsoft ドキュメント
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
ms.openlocfilehash: 7e51e4c425d3d16b57a2b1ce0d4fc2f585dc505d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378058"
---
# <a name="registering-ole-controls"></a>OLE コントロールの登録
その他の OLE サーバー オブジェクトと同様に、OLE コントロールは、他の OLE に対応するアプリケーションでアクセスできます。 これは、コントロールのタイプ ライブラリとクラスを登録することによって実現されます。  
  
 次の機能を追加して、Windows レジストリ データベースに、コントロールのクラス、プロパティ ページ、およびタイプ ライブラリを削除できます。  
  
### <a name="registering-ole-controls"></a>OLE コントロールの登録  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|コントロールのクラスを登録データベースに追加します。|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|登録情報データベースには、コントロールのプロパティ ページを追加します。|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|登録情報データベースには、コントロールのタイプ ライブラリを追加します。|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|登録情報データベースから、コントロール クラスまたはプロパティ ページ クラスを削除します。|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|コントロールのタイプ ライブラリを登録情報データベースから削除します。|  
  
 `AfxOleRegisterTypeLib` 通常の制御 DLL の実装で呼び出されます`DllRegisterServer`です。 同様に、`AfxOleUnregisterTypeLib`によって呼び出される`DllUnregisterServer`です。 `AfxOleRegisterControlClass`、 `AfxOleRegisterPropertyPageClass`、および`AfxOleUnregisterClass`によって呼び出される通常、`UpdateRegistry`コントロールのクラス ファクトリやプロパティ ページのメンバー関数。  
  
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
 `hInstance`  
 コントロール クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `pszProgID`  
 コントロールの一意なプログラム ID。  
  
 `idTypeName`  
 コントロールの種類のユーザーが判読できる名前を含む文字列のリソース ID です。  
  
 *idBitmap*  
 ツールバーまたはパレット内の OLE コントロールを表すために使用するビットマップのリソース ID です。  
  
 `nRegFlags`  
 次のフラグの 1 つ以上含まれています。  
  
- `afxRegInsertable` OLE オブジェクトのオブジェクトの挿入 ダイアログ ボックスに表示するには、制御できます。  
  
- `afxRegApartmentThreading` スレッド処理モデルを ThreadingModel をレジストリに設定アパートメントを = です。  
  
- `afxRegFreeThreading` スレッド処理モデルを ThreadingModel をレジストリに設定空きを = です。  
  
     2 つのフラグを組み合わせることができます`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both です。 参照してください[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)スレッド処理モデルの登録の詳細について Windows SDK に含まれています。  
  
> [!NOTE]
>  MFC 4.2 より前に、のバージョンの MFC で、 `int` `nRegFlags`パラメーターが指定されて、 **BOOL**パラメーター、 *bInsertable*、許可またはオブジェクトの挿入 ダイアログから挿入されるコントロールを禁止します。ボックスです。  
  
 *dwMiscStatus*  
 次の状態フラグの 1 つ以上含まれています (フラグの説明は、次を参照してください。**入ります**Windows SDK 内の列挙型)。  
  
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
  
 `wVerMajor`  
 コントロール クラスのメジャー バージョン番号。  
  
 `wVerMinor`  
 コントロール クラスのマイナー バージョン番号。  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、対応する OLE コントロールのコンテナーで使用するコントロール。 `AfxOleRegisterControlClass` コントロールの名前と、システム上の場所とレジストリを更新してもレジストリにコントロールをサポートする、スレッディング モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール、」と[に関するプロセスとスレッド](http://msdn.microsoft.com/library/windows/desktop/ms681917)Windows SDK にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 上記の例でどのように`AfxOleRegisterControlClass`で呼び出された用フラグ挿入可能なとフラグのアパートメント モデルの 6 番目のパラメーターを作成するには、一緒に論理和。  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 コントロールが有効になっているコンテナーは、オブジェクトの挿入 ダイアログ ボックスに表示されます、アパートメント モデルを認識があります。 アパートメント モデルに対応したコントロールは、必ず静的クラスのデータは、ロックで保護できるように、1 つのアパートメントでのコントロールは、静的データにアクセスするときに、無効になっていなかった、スケジューラによってそれが完了しを使用して、同じクラスの別のインスタンスを開始する前に同じ静的データです。 静的なデータへのアクセスは、クリティカル セクションのコードで囲まれます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Windows 登録データベースのプロパティ ページ クラスを登録します。  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 プロパティ ページ クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 `clsid`  
 プロパティ ページの一意のクラス ID。  
  
 `idTypeName`  
 プロパティ ページのユーザーが判読できる名前を表す文字列のリソース ID です。  
  
 `nRegFlags`  
 フラグを含めることがあります。  
  
- `afxRegApartmentThreading` スレッド処理モデルを ThreadingModel をレジストリに設定アパートメントを = です。  
  
> [!NOTE]
>  MFC 4.2 では、以前のバージョンの MFC で、 `int` `nRegFlags`パラメーターは使用できませんでした。 なお、`afxRegInsertable`フラグは、プロパティ ページの有効なオプションではないと、によって設定されている場合、MFC で ASSERT を実行  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、対応する OLE コントロールのコンテナーで使用するプロパティ ページ。 `AfxOleRegisterPropertyPageClass` プロパティ ページの名前と、システム上の場所でレジストリを更新しても、レジストリで、コントロールをサポートする、スレッディング モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール、」と[に関するプロセスとスレッド](http://msdn.microsoft.com/library/windows/desktop/ms681917)Windows SDK にします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Windows 登録データベースのタイプ ライブラリを登録し、OLE コントロールを認識するその他のコンテナーで使用されるタイプ ライブラリを使用します。  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 タイプ ライブラリに関連付けられているアプリケーションのインスタンス ハンドル。  
  
 *tlid*  
 タイプ ライブラリの一意の ID。  
  
 *pszFileName*  
 ローカライズされたタイプ ライブラリの省略可能なファイル名を指す (です。コントロールの TLB) ファイルです。  
  
 *pszHelpDir*  
 タイプ ライブラリのヘルプ ファイルがあるディレクトリの名前。 場合**NULL**、ヘルプ ファイルがそれ自体のタイプ ライブラリと同じディレクトリにあると見なされます。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが登録されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、タイプ ライブラリの名前と、システム上の場所とレジストリを更新します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Windows 登録情報データベースからのコントロールまたはプロパティ ページ クラスのエントリを削除します。  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>パラメーター  
 *clsID*  
 コントロールまたはプロパティ ページの一意のクラス ID。  
  
 `pszProgID`  
 コントロールまたはプロパティ ページの一意なプログラム ID。  
  
### <a name="return-value"></a>戻り値  
 コントロールまたはプロパティ ページ クラスが正常に登録できなかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Windows 登録情報データベースからタイプ ライブラリのエントリを削除するには、この関数を呼び出します。  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>パラメーター  
 `tlID`  
 タイプ ライブラリの一意の ID。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが正常に登録できなかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
