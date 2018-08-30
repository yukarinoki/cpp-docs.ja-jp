---
title: CSharedFile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs:
- C++
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38267ed5755b99bd97e4c923611d297673fcc41e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215584"
---
# <a name="csharedfile-class"></a>CSharedFile クラス
[CMemFile](../../mfc/reference/cmemfile-class.md)-共有メモリ ファイルをサポートするクラスを派生します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|`CSharedFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|共有メモリ ファイルを閉じて、そのメモリ ブロックのハンドルを返します。|  
|[CSharedFile::SetHandle](#sethandle)|メモリ ブロックには、共有メモリ ファイルをアタッチします。|  
  
## <a name="remarks"></a>Remarks  
 メモリのファイルは、ファイルがディスクではなく RAM に格納されていることを除いて、ディスク ファイルと同様に動作します。 メモリ ファイルは高速な一時ストレージまたは生バイトを転送するために役立ちます。 または、独立したプロセスの間でオブジェクトをシリアル化します。  
  
 使用してメモリが割り当てられた、他のメモリ ファイルの共有メモリ ファイルとは異なる、 [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows 関数。 `CSharedFile`クラスは、グローバルに割り当てられたメモリ ブロックにデータを保存 (を使用して作成`GlobalAlloc`)、このメモリ ブロックを共有できる DDE、クリップボード、またはその他の OLE と COM uniform データ転送操作、たとえばを使用してを使用して、`IDataObject`します。  
  
 `GlobalAlloc` によって返されたポインターなどのメモリへのポインターではなく、HGLOBAL がハンドルを返します[malloc](../../c-runtime-library/reference/malloc.md)します。 HGLOBAL ハンドルは、特定のアプリケーションで必要です。 たとえば、クリップボードにデータを格納する書き込むようが必要です。  
  
 なお、`CSharedFile`使用メモリ マップト ファイルではなくを行い、プロセス間でデータを直接共有することはできません。  
  
 `CSharedFile` 独自のメモリ ブロックをアタッチするオブジェクトが独自のメモリを自動的に割り当てることも、`CSharedFile`オブジェクトを呼び出すことによって[CSharedFile::SetHandle](#sethandle)します。 いずれの場合も、メモリ ファイルを自動的に拡大するためのメモリが割り当てられている`nGrowBytes`-場合分ずつ`nGrowBytes`がゼロでないです。  
  
 詳細については、この記事を参照してください。 [MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="csharedfile"></a>  CSharedFile::CSharedFile  
 構築、`CSharedFile`オブジェクトし、そのメモリを割り当てます。  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>パラメーター  
 *nAllocFlags*  
 メモリの割り当て方法を示すフラグです。 参照してください[GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)有効なフラグ値の一覧についてはします。  
  
 *nGrowBytes*  
 バイトのメモリ割り当てインクリメントします。  
  
##  <a name="detach"></a>  CSharedFile::Detach  
 メモリ ファイルを閉じるし、メモリ ブロックからデタッチするには、この関数を呼び出します。  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>戻り値  
 メモリのファイルの内容を格納するメモリ ブロックのハンドル。  
  
### <a name="remarks"></a>Remarks  
 呼び出すことによって開くことができます[SetHandle](#sethandle)、によって返されるハンドルを使用して**デタッチ**します。  
  
##  <a name="sethandle"></a>  CSharedFile::SetHandle  
 グローバル メモリのブロックを接続するには、この関数を呼び出し、`CSharedFile`オブジェクト。  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *hGlobalMemory*  
 接続するグローバル メモリへのハンドル、`CSharedFile`します。  
  
 *bAllowGrow*  
 メモリ ブロックに拡張できるかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 場合*bAllowGrow*が 0 以外の場合、メモリ ブロックのサイズはたとえば、この必要に応じて、増加が、うまくいかない場合に加えられたメモリ ブロックに割り当てられたよりもファイルにバイトを書き込みます。  
  
## <a name="see-also"></a>関連項目  
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)
