---
title: CMonikerFile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 296e288f017373563b867b02ad26f25ec6bc6227
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853648"
---
# <a name="cmonikerfile-class"></a>CMonikerFile クラス
データのストリームを表します ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) によってという名前を[IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|`CMonikerFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|デタッチし、ストリームを解放し、モニカーを解放します。|  
|[CMonikerFile::Detach](#detach)|デタッチ、`IMoniker`これから`CMonikerFile`オブジェクト。|  
|[CMonikerFile::GetMoniker](#getmoniker)|現在のモニカーを返します。|  
|[CMonikerFile::Open](#open)|ストリームを取得する指定されたファイルを開きます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|バインド コンテキストを取得するか、既定値に初期化のバインド コンテキストを作成します。|  
  
## <a name="remarks"></a>Remarks  
 モニカーには、ファイルへのパス名のような情報が含まれています。 モニカー オブジェクトへのポインターがあるかどうかは`IMoniker`インターフェイス、ファイルが実際に配置されている場所に関するその他の特定の情報をしなくても、特定のファイルへのアクセスを取得できます。  
  
 派生した`COleStreamFile`、`CMonikerFile`モニカーまたはモニカーに行うことができますの文字列表現を受け取り、モニカーは名前のストリームにバインドします。 読み取りし、そのストリームに書き込むことができます。 真の目的は、`CMonikerFile`簡単なアクセスを提供することです`IStream`s を付けた名前`IMoniker`s、自分でストリームにバインドする必要はありませんようにまだが`CFile`ストリームに機能します。  
  
 `CMonikerFile` ストリーム以外にバインドするのには使用できません。 使用する必要がありますストレージまたはオブジェクトにバインドする場合、`IMoniker`インターフェイスを直接します。  
  
 ストリームとモニカーの詳細については、次を参照してください[COleStreamFile](../../mfc/reference/colestreamfile-class.md)で、 *MFC リファレンス*と[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)と[IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)で、。Windows SDK。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxole.h  
  
##  <a name="close"></a>  CMonikerFile::Close  
 デタッチ後に、ストリームを解放し、モニカーを解放する、この関数を呼び出します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarks  
 開かれていない、または既に閉じられているストリームで呼び出すことができます。  
  
##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile  
 `CMonikerFile` オブジェクトを構築します。  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext  
 既定値に初期化のバインド コンテキストを作成するには、この関数を呼び出します。  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>パラメーター  
 *pError*  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 バインド コンテキストへのポインター [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)成功。 それ以外の場合に NULL の場合は、バインドします。 インスタンスが開かれた場合、`IBindHost`バインド コンテキストがから取得した、インターフェイス、 `IBindHost`。 存在する場合ありません`IBindHost`インターフェイスまたはインターフェイスは、バインド コンテキストに失敗した場合、バインド コンテキストが作成されます。 説明については、 [IBindHost](http://msdn.microsoft.com/library/ie/ms775076)インターフェイス、Windows SDK を参照してください。  
  
### <a name="remarks"></a>Remarks  
 バインド コンテキストは、特定のモニカー バインド操作に関する情報を格納するオブジェクトです。 カスタム バインド コンテキストを提供するには、この関数をオーバーライドすることができます。  
  
##  <a name="detach"></a>  CMonikerFile::Detach  
 ストリームを閉じるには、この関数を呼び出します。  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pError*  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker  
 現在のモニカーへのポインターを取得するには、この関数を呼び出します。  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のモニカー インターフェイスへのポインター ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705))。  
  
### <a name="remarks"></a>Remarks  
 `CMonikerFile` 、インターフェイスではありませんから返されるポインターは参照カウントをインクリメントしていません (を通じて[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379))、モニカーがリリースされたときに、`CMonikerFile`オブジェクトを解放します。 モニカーの保持またはそれを解放する場合は、まず`AddRef`こと。  
  
##  <a name="open"></a>  CMonikerFile::Open  
 ファイルまたはモニカー オブジェクトを開くには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszURL*  
 URL またはに開かれるファイルのファイル名。  
  
 *pError*  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
 *pMoniker*  
 モニカー インターフェイスへのポインター`IMoniker`ストリームを取得できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 *LpszURL* Macintosh でパラメーターを使用することはできません。 のみ、 *pMoniker*のフォーム`Open`Macintosh 上で使用できます。  
  
 URL またはファイルの名前を使用することができます、 *lpszURL*パラメーター。 例えば:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - または  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [COleStreamFile クラス](../../mfc/reference/colestreamfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)
