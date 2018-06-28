---
title: CMemFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e13c3b609a53e8c885e04530995a11218bf2704d
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040065"
---
# <a name="cmemfile-class"></a>CMemFile クラス
[CFile](../../mfc/reference/cfile-class.md)-メモリ ファイルをサポートするクラスを派生します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|メモリ ファイル オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|メモリ ブロックをアタッチ`CMemFile`です。|  
|[CMemFile::Detach](#detach)|メモリ ブロックを切り離します`CMemFile`デタッチされたメモリ ブロックへのポインターを返します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|メモリ割り当ての動作を変更するためにオーバーライドします。|  
|[CMemFile::Free](#free)|メモリの割り当て解除の動作を変更するためにオーバーライドします。|  
|[CMemFile::GrowFile](#growfile)|ファイルを拡張するときの動作を変更するためにオーバーライドします。|  
|[CMemFile::Memcpy](#memcpy)|ファイルを読み書きするときに、メモリ コピー動作を変更するためにオーバーライドします。|  
|[CMemFile::Realloc](#realloc)|メモリ割り当ての変更の動作を変更するためにオーバーライドします。|  
  
## <a name="remarks"></a>Remarks  
 これらのメモリ ファイルは、ファイルはディスクではなく RAM に保存する点を除いて、ディスク ファイルと同様に動作します。 メモリ ファイルは高速に一時的なストレージまたは生バイトを転送するために役立ちます。 または、独立したプロセス間でオブジェクトをシリアル化します。  
  
 `CMemFile` オブジェクトは、独自のメモリを自動的に割り当てることができますか、独自のメモリ ブロックを割り当てることができます、`CMemFile`呼び出して[アタッチ](#attach)です。 いずれの場合、メモリ ファイルを自動的に拡張にメモリが割り当てられます`nGrowBytes`-場合分ずつ`nGrowBytes`が 0 でないです。  
  
 メモリ ブロックの破棄後に自動的に削除されます、`CMemFile`オブジェクトで最初にメモリが割り当てられたかどうか、`CMemFile`オブジェクトです。 それ以外の場合、オブジェクトに関連付けられているメモリを解放する責任があります。  
  
 デタッチするときに提供されるポインターを通じてメモリ ブロックにアクセスすることができます、`CMemFile`呼び出して[デタッチ](#detach)です。  
  
 最も一般的な使用`CMemFile`を作成するには、`CMemFile`オブジェクトを呼び出すことによってこれを使用して[CFile](../../mfc/reference/cfile-class.md)メンバー関数。 作成することに注意してください、`CMemFile`それが自動的に開きます: 呼び出さない[CFile::Open](../../mfc/reference/cfile-class.md#open)、ディスク ファイルにのみ使用されます。 `CMemFile`ディスク ファイル、データ メンバーを使用しない`CFile::m_hFile`は使用されません。  
  
 `CFile`メンバー関数[複製](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)は適用されていない`CMemFile`です。 これらの関数を呼び出す場合、`CMemFile`オブジェクトを取得するが、[行わない](../../mfc/reference/cnotsupportedexception-class.md)です。  
  
 `CMemFile` ランタイム ライブラリ関数を使用して[malloc](../../c-runtime-library/reference/malloc.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、および[空き](../../c-runtime-library/reference/free.md)割り当てるには、再割り当て、およびメモリと、組み込みの割り当てを解除[memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)ブロックの読み取りまたは書き込み時に、メモリをコピーします。 この動作または動作を変更するかかどうかとき`CMemFile`、ファイルが拡張から独自のクラスを派生させる`CMemFile`し、適切な関数をオーバーライドします。  
  
 詳細については`CMemFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[メモリ管理 (MFC)](../../mfc/memory-management.md)しを参照してください[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイムライブラリ リファレンス*です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afx.h  
  
##  <a name="alloc"></a>  CMemFile::Alloc  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBytes*  
 割り当てられるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、割り当てが失敗します。  
  
### <a name="remarks"></a>Remarks  
 独自のメモリ割り当てを実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[空き](#free)と[Realloc](#realloc)もします。  
  
 既定の実装は、ランタイム ライブラリ関数を使用して[malloc](../../c-runtime-library/reference/malloc.md)メモリを割り当てられません。  
  
##  <a name="attach"></a>  CMemFile::Attach  
 メモリ ブロックをアタッチするには、この関数を呼び出す`CMemFile`です。  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpBuffer*  
 アタッチされているバッファーへのポインター`CMemFile`です。  
  
 *nBufferSize*  
 バッファーのサイズをバイト単位で指定する整数。  
  
 *nGrowBytes*  
 メモリ割り当て増分値 (バイト単位)。  
  
### <a name="remarks"></a>Remarks  
 これにより、`CMemFile`メモリ ファイルとしてのメモリ ブロックを使用します。  
  
 場合*nGrowBytes* 0 の場合は、`CMemFile`にファイルの長さを設定*nBufferSize*です。 つまり、このメモリ ブロック内のデータに割り当てられる前に`CMemFile`ファイルとして使用されます。 この方法で作成されたメモリ ファイルは拡張できません。  
  
 ファイルを拡張することはできません、ために発生しないように注意する`CMemFile`ファイルを拡張しようとします。 などは呼び出さないでください、`CMemFile`の上書きが[CFile:Write](../../mfc/reference/cfile-class.md#write)に末尾の書き込みまたは呼び出さないでください[CFile:SetLength](../../mfc/reference/cfile-class.md#setlength)長がよりも長い*nBufferSize*です。  
  
 場合*nGrowBytes*は 0 より大きく、`CMemFile`添付したメモリ ブロックの内容は無視されます。 スクラッチを使用してから、メモリ ファイルの内容を記述する必要があります、`CMemFile`のオーバーライド`CFile::Write`です。 ファイルの末尾を越えて書き込みまたは呼び出すことによって、ファイルを拡張しようとすると、`CMemFile`のオーバーライド`CFile::SetLength`、`CMemFile`単位でメモリの割り当てが大きくなり*nGrowBytes*です。 メモリ ブロックを渡す場合は失敗、メモリ割り当てを拡大して`Attach`と互換性のあるメソッドで割り当てられていない[アロケーション](#alloc)します。 既定の実装との互換性を`Alloc`、ランタイム ライブラリ関数でメモリを割り当てる必要があります[malloc](../../c-runtime-library/reference/malloc.md)または[calloc](../../c-runtime-library/reference/calloc.md)です。  
  
##  <a name="cmemfile"></a>  CMemFile::CMemFile  
 最初のオーバー ロードは、空のメモリ ファイルを開きます。  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nGrowBytes*  
 メモリ割り当て増分値 (バイト単位)。  
  
 *lpBuffe*r  
 サイズの情報を受け取るバッファーへのポインター *nBufferSize*です。  
  
 *nBufferSize*  
 ファイル バッファーのサイズをバイト単位で指定する整数。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターによって、ファイルが開かれていると、呼び出す必要がありますいないことに注意してください[CFile::Open](../../mfc/reference/cfile-class.md#open)です。  
  
 2 番目のオーバー ロードは、動作は同じように場合、最初のコンス トラクターを使用して、すぐと呼ばれる[アタッチ](#attach)同じパラメーターを使用します。 詳細については、「`Attach`」を参照してください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>  CMemFile::Detach  
 によって使用されているメモリ ブロックへのポインターを取得するには、この関数を呼び出す`CMemFile`です。  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 メモリ ファイルの内容を保持するメモリ ブロックへのポインター。  
  
### <a name="remarks"></a>Remarks  
 閉じますでこの関数を呼び出す、`CMemFile`です。 メモリ ブロックを再アタッチできます`CMemFile`を呼び出して[アタッチ](#attach)です。 ファイルを再アタッチし、データを使用する場合を呼び出す必要があります[結び付けてその中](../../mfc/reference/cfile-class.md#getlength)を呼び出す前にファイルの長さを取得する`Detach`です。 メモリ ブロックをアタッチする場合は、`CMemFile`そのデータを使用できるように ( `nGrowBytes` = = 0)、メモリ ファイルを拡張することはできませんし、します。  
  
##  <a name="free"></a>  CMemFile::Free  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMem*  
 解放するメモリへのポインター。  
  
### <a name="remarks"></a>Remarks  
 カスタムのメモリの解放を実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[アロケーション](#alloc)と[Realloc](#realloc)もします。  
  
##  <a name="growfile"></a>  CMemFile::GrowFile  
 この関数は、いくつかの`CMemFile`メンバー関数。  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwNewLen*  
 メモリ ファイルの新しいサイズ。  
  
### <a name="remarks"></a>Remarks  
 変更する場合に上書きできる方法`CMemFile`そのファイルが拡張されます。 既定の実装[Realloc](#realloc)を既存のブロックを拡張する (または[アロケーション](#alloc)メモリ ブロックを作成する) の倍数でメモリを割り当て、`nGrowBytes`コンス トラクターで指定された値または[アタッチ](#attach)呼び出します。  
  
##  <a name="memcpy"></a>  CMemFile::Memcpy  
 この関数は、`CMemFile`の上書きが[:read](../../mfc/reference/cfile-class.md#read)と[CFile::Write](../../mfc/reference/cfile-class.md#write)とメモリ ファイルからデータを転送します。  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMemTarget*  
 ソースのメモリのコピー先のメモリ ブロックへのポインター。  
  
 *lpMemSource*  
 元のメモリ ブロックへのポインター。  
  
 *nBytes*  
 コピー対象のバイト数。  
  
### <a name="return-value"></a>戻り値  
 コピー *lpMemTarget*です。  
  
### <a name="remarks"></a>Remarks  
 方法を変更する場合は、この関数をオーバーライドする`CMemFile`はメモリをコピーします。  
  
##  <a name="realloc"></a>  CMemFile::Realloc  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMem*  
 再割り当てするメモリ ブロックへのポインター。  
  
 *nBytes*  
 メモリ ブロックの新しいサイズ。  
  
### <a name="return-value"></a>戻り値  
 再割り当て (され、場合によって移動)、メモリ ブロックへのポインターまたは**NULL**再割り当てが失敗した場合。  
  
### <a name="remarks"></a>Remarks  
 カスタムのメモリ割り当ての変更を実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[アロケーション](#alloc)と[空き](#free)もします。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



