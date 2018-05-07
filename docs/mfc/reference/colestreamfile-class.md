---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 805c32145d844cc1103cab7c4987c0595ff5935f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="colestreamfile-class"></a>関数クラス
データのストリームを表します ( `IStream`) OLE 構造化記憶の一部として、複合ファイルでします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|`COleStreamFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|ストリームをオブジェクトに関連付けます。|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|グローバル メモリからストリームを作成し、オブジェクトに関連付けます。|  
|[COleStreamFile::CreateStream](#createstream)|ストリームを作成し、オブジェクトに関連付けます。|  
|[COleStreamFile::Detach](#detach)|オブジェクトからストリームの関連付けを解除します。|  
|[COleStreamFile::GetStream](#getstream)|現在のストリームを返します。|  
|[COleStreamFile::OpenStream](#openstream)|安全にストリームを開いてをオブジェクトに関連付けます。|  
  
## <a name="remarks"></a>コメント  
 `IStorage`ストリームを開くか、メモリ ストリームである限り、作成する前にオブジェクトが存在する必要があります。  
  
 `COleStreamFile` 同様にオブジェクトが操作される[CFile](../../mfc/reference/cfile-class.md)オブジェクト。  
  
 ストリームとストレージ操作の詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md)..  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)と[IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="attach"></a>  COleStreamFile::Attach  
 指定された OLE ストリームを関連付ける、`COleStreamFile`オブジェクト。  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStream`  
 OLE ストリームを指す ( `IStream`) オブジェクトに関連付ける。 ことはできません**NULL**です。  
  
### <a name="remarks"></a>コメント  
 オブジェクトおく必要がありますいない OLE ストリームに関連付けられています。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK に含まれています。  
  
##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile  
 
          `COleStreamFile` オブジェクトを作成します。  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStream`  
 オブジェクトと関連付けられる OLE ストリームへのポインター。  
  
### <a name="remarks"></a>コメント  
 場合`lpStream`は**NULL**オブジェクトに関連付けられていない OLE ストリーム、それ以外の場合、オブジェクトは、指定された OLE ストリームに関連付けられています。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK に含まれています。  
  
##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream  
 安全に、通常は、失敗、グローバル共有メモリが不足して、新しいストリームを作成します。  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**作成操作の完了状態を示すです。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メモリは、OLE サブシステムによって割り当てられます。  
  
 詳細については、次を参照してください。 [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) Windows SDK に含まれています。  
  
##  <a name="createstream"></a>  COleStreamFile::CreateStream  
 安全に、通常は、失敗、指定されたストレージ オブジェクトに新しいストリームを作成します。  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStorage`  
 作成するストリームを含む OLE ストレージ オブジェクトへのポインター。 ことはできません**NULL**です。  
  
 `lpszStreamName`  
 作成されるストリームの名前です。 ことはできません**NULL**です。  
  
 `nOpenFlags`  
 ストリームを開くときに使用するアクセス モード。 排他的、読み取り/書き込み、および作成モードは既定で使用します。 使用可能なモードの完全な一覧を参照してください。[ほか](../../mfc/reference/cfile-class.md#cfile)です。  
  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**です。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オープンに失敗した場合、ファイルの例外がスローされますと`pError`は**NULL**です。  
  
 詳細については、次を参照してください。 [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) Windows SDK に含まれています。  
  
##  <a name="detach"></a>  COleStreamFile::Detach  
 ストリームを閉じることがなく、オブジェクトからストリームの関連付けを解除します。  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>戻り値  
 ストリームへのポインター ( `IStream`) が、オブジェクトに関連付けられています。  
  
### <a name="remarks"></a>コメント  
 プログラムが終了する前に、その他の何らかの方法でストリームを閉じる必要があります。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK に含まれています。  
  
##  <a name="getstream"></a>  COleStreamFile::GetStream  
 この関数では、現在のストリームへのポインターを返します。  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のストリーム インターフェイスへのポインター ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034))。  
  
##  <a name="openstream"></a>  COleStreamFile::OpenStream  
 既存のストリームを開きます。  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStorage`  
 開かれるストリームを含む OLE ストレージ オブジェクトへのポインター。 ことはできません**NULL**です。  
  
 `lpszStreamName`  
 開かれるストリームの名前です。 ことはできません**NULL**です。  
  
 `nOpenFlags`  
 ストリームを開くときに使用するアクセス モード。 排他的読み取り/書き込みモードは既定で使用されます。 使用可能なモードの完全な一覧については[ほか](../../mfc/reference/cfile-class.md#cfile)です。  
  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**です。 ストリームを開こうとしたによって生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に開かれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オープンに失敗した場合、ファイルの例外がスローされますと`pError`は**NULL**です。  
  
 詳細については、次を参照してください。 [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



