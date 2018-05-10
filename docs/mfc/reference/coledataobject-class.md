---
title: COleDataObject クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDataObject
- AFXOLE/COleDataObject
- AFXOLE/COleDataObject::COleDataObject
- AFXOLE/COleDataObject::Attach
- AFXOLE/COleDataObject::AttachClipboard
- AFXOLE/COleDataObject::BeginEnumFormats
- AFXOLE/COleDataObject::Detach
- AFXOLE/COleDataObject::GetData
- AFXOLE/COleDataObject::GetFileData
- AFXOLE/COleDataObject::GetGlobalData
- AFXOLE/COleDataObject::GetNextFormat
- AFXOLE/COleDataObject::IsDataAvailable
- AFXOLE/COleDataObject::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDataObject [MFC], COleDataObject
- COleDataObject [MFC], Attach
- COleDataObject [MFC], AttachClipboard
- COleDataObject [MFC], BeginEnumFormats
- COleDataObject [MFC], Detach
- COleDataObject [MFC], GetData
- COleDataObject [MFC], GetFileData
- COleDataObject [MFC], GetGlobalData
- COleDataObject [MFC], GetNextFormat
- COleDataObject [MFC], IsDataAvailable
- COleDataObject [MFC], Release
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9cd159597440dfb55bbe8abe147623096cdf449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coledataobject-class"></a>COleDataObject クラス
クリップボードや OLE 埋め込みアイテムからさまざまなフォーマットのデータを取得するときのデータ転送に使用します。クリップボードからデータを取得するときは、ドラッグ アンド ドロップを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDataObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::COleDataObject](#coledataobject)|`COleDataObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDataObject::Attach](#attach)|指定された OLE データ オブジェクトをアタッチ、`COleDataObject`です。|  
|[COleDataObject::AttachClipboard](#attachclipboard)|クリップボードにデータ オブジェクトをアタッチします。|  
|[COleDataObject::BeginEnumFormats](#beginenumformats)|1 つまたは複数後続準備`GetNextFormat`呼び出しです。|  
|[COleDataObject::Detach](#detach)|関連付けられたデタッチ`IDataObject`オブジェクト。|  
|[COleDataObject::GetData](#getdata)|指定した形式で、アタッチされた OLE データ オブジェクトからのデータをコピーします。|  
|[COleDataObject::GetFileData](#getfiledata)|接続された OLE データ オブジェクトからデータをコピー、`CFile`指定された形式でのポインター。|  
|[COleDataObject::GetGlobalData](#getglobaldata)|接続された OLE データ オブジェクトからデータをコピー、`HGLOBAL`指定された形式でします。|  
|[COleDataObject::GetNextFormat](#getnextformat)|次のデータ形式を返します。|  
|[COleDataObject::IsDataAvailable](#isdataavailable)|データが指定された形式で使用できるかどうかを確認します。|  
|[COleDataObject::Release](#release)|関連付けを解除し、関連付けられた解放`IDataObject`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `COleDataObject` 基本クラスはありません。  
  
 これらのデータ転送には、ソースおよび変換先が含まれます。 オブジェクトとしてデータ ソースが実装されている、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クラスです。 転送先アプリケーションがドロップされるデータが含まれてまたはのオブジェクト、クリップボードから貼り付け操作の実行を促すメッセージが表示されるたびに、`COleDataObject`クラスを作成する必要があります。  
  
 このクラスでは、指定した形式でデータが存在するかどうかを確認することができます。 使用可能なデータ形式を列挙または特定の形式が使用できるかどうかを確認し、推奨される形式でデータを取得できます。 オブジェクトの取得の使用など、さまざまな方法で達成できる、 [CFile](../../mfc/reference/cfile-class.md)、 `HGLOBAL`、または**STGMEDIUM**構造体。  
  
 詳細については、次を参照してください。、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) Windows SDK 内の構造。  
  
 詳細については、アプリケーションでデータ オブジェクトを使用して、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `COleDataObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="attach"></a>  COleDataObject::Attach  
 この関数に関連付けるには、 `COleDataObject` OLE データ オブジェクトを持つオブジェクト。  
  
```  
void Attach(
    LPDATAOBJECT lpDataObject,  
    BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDataObject*  
 OLE データ オブジェクトへのポインター。  
  
 `bAutoRelease`  
 **TRUE** OLE データ オブジェクトがある場合リリースされたときに、`COleDataObject`オブジェクトが破棄された**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421) Windows SDK に含まれています。  
  
##  <a name="attachclipboard"></a>  COleDataObject::AttachClipboard  
 現在クリップボードにあるデータ オブジェクトをアタッチするには、この関数を呼び出して、`COleDataObject`オブジェクト。  
  
```  
BOOL AttachClipboard();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  この関数を呼び出すことでは、このデータ オブジェクトが解放されるまでに、クリップボードをロックします。 デストラクターではデータ オブジェクトの解放、`COleDataObject`です。 詳細については、次を参照してください。 [OpenClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649048)と[CloseClipboard](http://msdn.microsoft.com/library/windows/desktop/ms649035) Win32 ドキュメントにします。  
  
##  <a name="beginenumformats"></a>  COleDataObject::BeginEnumFormats  
 後続の呼び出しを準備するには、この関数を呼び出す`GetNextFormat`項目からのデータ形式の一覧を取得するためです。  
  
```  
void BeginEnumFormats();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しの後に`BeginEnumFormats`、このデータ オブジェクトでサポートされている最初の形式の位置を格納します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。  
  
 確認するには、指定された形式でデータの可用性を使用して[COleDataObject::IsDataAvailable](#isdataavailable)です。  
  
 詳細については、次を参照してください。 [IDataObject::EnumFormatEtc](http://msdn.microsoft.com/library/windows/desktop/ms683979) Windows SDK に含まれています。  
  
##  <a name="coledataobject"></a>  COleDataObject::COleDataObject  
 `COleDataObject` オブジェクトを構築します。  
  
```  
COleDataObject();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[COleDataObject::Attach](#attach)または[COleDataObject::AttachClipboard](#attachclipboard)他を呼び出す前に行う必要があります`COleDataObject`関数。  
  
> [!NOTE]
>  ポインターをドラッグ アンド ドロップのハンドラーに渡すパラメーターの 1 つは、 `COleDataObject`、ドラッグ アンド ドロップをサポートするためにこのコンス トラクターを呼び出す必要はありません。  
  
##  <a name="detach"></a>  COleDataObject::Detach  
 デタッチするには、この関数を呼び出して、`COleDataObject`オブジェクトからのデータ オブジェクトを解放せず、その関連付けられた OLE データ オブジェクト。  
  
```  
LPDATAOBJECT Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされた OLE データ オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdata"></a>  COleDataObject::GetData  
 この関数では、指定された形式で項目からデータを取得します。  
  
```  
BOOL GetData(
    CLIPFORMAT cfFormat,  
    LPSTGMEDIUM lpStgMedium,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データを受け取る構造体。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 場合は**NULL**、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getfiledata"></a>  COleDataObject::GetFileData  
 作成するには、この関数を呼び出して、`CFile`または`CFile`-派生オブジェクトに指定された形式でデータを取得して、`CFile`ポインター。  
  
```  
CFile* GetFileData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 場合は**NULL**、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 新しいポインター`CFile`または`CFile`-成功した場合は、データを格納している派生オブジェクト**NULL**です。  
  
### <a name="remarks"></a>コメント  
 データが格納されている中、によって、戻り値によって示される実際の型があります`CFile`、 `CSharedFile`、または`COleStreamFile`です。  
  
> [!NOTE]
>  `CFile`この関数の戻り値によってアクセスされるオブジェクトには、呼び出し元が所有します。 呼び出し元の役割です**削除**、`CFile`をファイルを閉じる。  
  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getglobaldata"></a>  COleDataObject::GetGlobalData  
 この関数に指定された形式でデータを取得してグローバル メモリ ブロックを割り当てる、`HGLOBAL`です。  
  
```  
HGLOBAL GetGlobalData(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 データが返される形式です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データが返される形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合、このパラメーターの値を指定`cfFormat`です。 場合は**NULL**、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、データを含むグローバル メモリ ブロックのハンドルそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
##  <a name="getnextformat"></a>  COleDataObject::GetNextFormat  
 この関数では、繰り返しを項目からデータを取得するために使用可能なすべての形式を取得します。  
  
```  
BOOL GetNextFormat(LPFORMATETC lpFormatEtc);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)関数呼び出しが戻るときの書式情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 別の形式がある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しの後に[COleDataObject::BeginEnumFormats](#beginenumformats)、このデータ オブジェクトでサポートされている最初の形式の位置を格納します。 連続して呼び出す`GetNextFormat`データ オブジェクトで使用可能な形式の一覧を列挙します。 これらの関数を使用して、使用可能な形式の一覧します。  
  
 指定した形式の可用性を確認するには、呼び出す[COleDataObject::IsDataAvailable](#isdataavailable)です。  
  
 詳細については、次を参照してください。 [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) Windows SDK に含まれています。  
  
##  <a name="isdataavailable"></a>  COleDataObject::IsDataAvailable  
 この関数では、特定の形式が OLE 項目からデータを取得するために使用できるかを判断します。  
  
```  
BOOL IsDataAvailable(
    CLIPFORMAT cfFormat,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cfFormat`  
 構造体で使用されるクリップボードのデータ形式を指す`lpFormatEtc`です。 このパラメーターには、定義済みのクリップボード形式またはネイティブの Windows で返される値のいずれかを指定できます[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数。  
  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)目的の形式を記述する構造体。 指定されたクリップボードの形式の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`です。 場合は**NULL**、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 指定された形式でデータがある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は呼び出しの前に`GetData`、 `GetFileData`、または`GetGlobalData`です。  
  
 詳細については、次を参照してください。 [IDataObject::QueryGetData](http://msdn.microsoft.com/library/windows/desktop/ms680637)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK に含まれています。  
  
 詳細については、次を参照してください。[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[CRichEditView::QueryAcceptData](../../mfc/reference/cricheditview-class.md#queryacceptdata)です。  
  
##  <a name="release"></a>  COleDataObject::Release  
 所有権を解放するには、この関数を呼び出して、 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421)が以前関連付けられているオブジェクト、`COleDataObject`オブジェクト。  
  
```  
void Release();
```  
  
### <a name="remarks"></a>コメント  
 `IDataObject`が関連付けられて、`COleDataObject`を呼び出して**アタッチ**または`AttachClipboard`明示的にまたは framework。 場合、`bAutoRelease`のパラメーター**アタッチ**は**FALSE**、`IDataObject`オブジェクトは解放されません。 この場合、呼び出し元が解放を担当する、`IDataObject`を呼び出して[iunknown::release](http://msdn.microsoft.com/library/windows/desktop/ms682317)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataSource クラス](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)
