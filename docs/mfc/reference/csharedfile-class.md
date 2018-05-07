---
title: 関数クラス |Microsoft ドキュメント
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
ms.openlocfilehash: bee22940fb197d480f4ae3550d8dd59780c256b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="csharedfile-class"></a>関数クラス
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
|[CSharedFile::Detach](#detach)|共有メモリ ファイルを閉じ、そのメモリ ブロックのハンドルを返します。|  
|[CSharedFile::SetHandle](#sethandle)|メモリ ブロックへの共有メモリ ファイルをアタッチします。|  
  
## <a name="remarks"></a>コメント  
 メモリ ファイルは、ファイルはディスクではなく RAM に保存する点を除いて、ディスク ファイルと同様に動作します。 メモリ ファイルは高速に一時的なストレージまたは生バイトを転送するために役立ちます。 または、独立したプロセス間でオブジェクトをシリアル化します。  
  
 共有メモリ ファイルとは異なり、他のメモリ ファイルから使用するためのメモリが割り当てられた、 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows の機能です。 `CSharedFile`クラスは、グローバルに割り当てられたメモリ ブロックにデータを格納 (を使用して作成**GlobalAlloc**)、DDE、クリップボード、またはその他の OLE と COM uniform データ転送操作、たとえばを使用してこのメモリ ブロックを共有することができます使用して`IDataObject`です。  
  
 **GlobalAlloc**を返します、`HGLOBAL`などによって返されるポインターのメモリへのポインターではなく処理[malloc](../../c-runtime-library/reference/malloc.md)です。 `HGLOBAL`ハンドルは、特定のアプリケーションで必要です。 たとえば、データに置くクリップボードする必要があります、`HGLOBAL`を処理します。  
  
 なお、`CSharedFile`使用メモリ マップト ファイルではなくを行い、プロセス間でデータを直接共有することはできません。  
  
 `CSharedFile` オブジェクトは、独自のメモリを自動的に割り当てることができますか、独自のメモリ ブロックを割り当てることができます、`CSharedFile`呼び出して[CSharedFile::SetHandle](#sethandle)です。 いずれの場合、メモリ ファイルを自動的に拡張にメモリが割り当てられます`nGrowBytes`-場合分ずつ`nGrowBytes`が 0 でないです。  
  
 詳細については、記事を参照してください。 [MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="csharedfile"></a>  CSharedFile::CSharedFile  
 構築、`CSharedFile`オブジェクトし、それにメモリを割り当てます。  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>パラメーター  
 *nAllocFlags*  
 メモリの割り当て方法を示すフラグです。 参照してください[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)有効なフラグ値の一覧についてはします。  
  
 `nGrowBytes`  
 メモリ割り当て増分値 (バイト単位)。  
  
##  <a name="detach"></a>  CSharedFile::Detach  
 この関数では、ファイルを閉じて、メモリ、メモリ ブロックからデタッチします。  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>戻り値  
 メモリ ファイルの内容を保持するメモリ ブロックのハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出すことによって開くことができます[SetHandle](#sethandle)、によって返されるハンドルを使用して**デタッチ**です。  
  
##  <a name="sethandle"></a>  CSharedFile::SetHandle  
 使用するグローバル メモリのブロックをアタッチするには、この関数を呼び出して、`CSharedFile`オブジェクト。  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *hGlobalMemory*  
 接続するグローバル メモリへのハンドル、`CSharedFile`です。  
  
 `bAllowGrow`  
 メモリ ブロックの拡張が許可されたかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`bAllowGrow`が 0 でないため、メモリ ブロックのサイズはたとえば、この、必要に応じて増加しようとしてがの場合行われたファイルに書き込むバイト数、メモリ ブロックの割り当てられたよりもします。  
  
## <a name="see-also"></a>関連項目  
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)
