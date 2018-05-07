---
title: OLE の初期化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8224cf27313b056b95990f514e02eb9d9c08cad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-initialization"></a>OLE の初期化
アプリケーションでは、OLE システム サービスを使用できます、前に OLE システム Dll の初期化する必要があり、Dll が適切なバージョンであることを確認します。 **AfxOleInit**関数を OLE システム Dll を初期化します。  
  
### <a name="ole-initialization"></a>OLE の初期化  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|OLE ライブラリを初期化します。| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|アプリケーション オブジェクトのこの関数の呼び出し`InitInstance`OLE コントロールのコンテインメントのサポートを有効にする関数。| 


## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer
アプリケーション オブジェクトのこの関数の呼び出し`InitInstance`OLE コントロールのコンテインメントのサポートを有効にする関数。  
   
### <a name="syntax"></a>構文    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>コメント  
 (ActiveX コントロールと呼ばれるようになりました) OLE コントロールの詳細については、次を参照してください。 [ActiveX コントロールのトピック](../mfc-activex-controls.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  

  
##  <a name="afxoleinit"></a>  AfxOleInit  
 アプリケーションの OLE サポートを初期化します。  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外の値です。初期化に失敗した場合は 0 です。失敗の原因は多くの場合、正しくないバージョンの OLE システム DLL がインストールされていることです。  
  
### <a name="remarks"></a>コメント  
 MFC アプリケーションに対する OLE サポートを初期化するには、この関数を呼び出します。 この関数を呼び出すと、次のアクションが発生します。  
  
-   呼び出し元のアプリケーションの現在のアパートメントで COM ライブラリを初期化します。 詳細については、次を参照してください。 [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134)です。  
  
-   メッセージ フィルター オブジェクトを作成を実装する、 [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740)インターフェイスです。 このメッセージ フィルターの呼び出しでアクセスできる[AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)です。  
  
> [!NOTE]
>  場合**AfxOleInit**が呼び出された MFC dll の場合は、呼び出しは失敗します。 この関数は DLL から呼び出された場合、呼び出し元アプリケーションによって OLE システムが既に初期化されていることを想定するため、失敗が生じます。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)で、`InitInstance`オーバーライドで指定`COINIT_APARTMENTTHREADED`(なく`COINIT_MULTITHREADED`)。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)です。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
