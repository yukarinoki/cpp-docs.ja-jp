---
title: CAtlFileMappingBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e315a29f72c887b5bff2e8177e7a47aed18c3fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364445"
---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase クラス
このクラスは、メモリ マップト ファイルを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|コンストラクターです。|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|ファイル マッピング オブジェクトからコピーするには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetData](#getdata)|このメソッドを呼び出してファイル マップ オブジェクトからデータを取得します。|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|このメソッドを呼び出してファイル ハンドルを返します。|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|ファイル マッピング オブジェクトからマッピングのサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapFile](#mapfile)|ファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|このメソッドを呼び出してファイル マッピング オブジェクトへのハンドルを返します。|  
|[CAtlFileMappingBase::Unmap](#unmap)|ファイル マッピング オブジェクトをマップ解除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|現在のファイル マッピング オブジェクトを別のファイル マッピング オブジェクトに設定します。|  
  
## <a name="remarks"></a>コメント  
 ファイルのマッピングは、プロセスの仮想アドレス空間の一部にファイルの内容の関連付けです。 このクラスは、プログラムを簡単にアクセスしてデータを共有するファイル マッピング オブジェクトを作成するためのメソッドを提供します。  
  
 詳細については、次を参照してください。[ファイル マップ](http://msdn.microsoft.com/library/windows/desktop/aa366556)Windows SDK に含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase  
 コンストラクターです。  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 新しいオブジェクトを作成するコピー元のファイル マッピング オブジェクト。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、既存のオブジェクトを使用して、新しいファイル マッピング オブジェクトを作成します。 呼び出す必要が[CAtlFileMappingBase::MapFile](#mapfile)を開くか、特定のファイルのファイル マッピング オブジェクトを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 デストラクターです。  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 クラスおよび呼び出しによって割り当てられているリソースを解放、 [CAtlFileMappingBase::Unmap](#unmap)メソッドです。  
  
##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom  
 ファイル マッピング オブジェクトからコピーするには、このメソッドを呼び出します。  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 コピーを元のファイル マッピング オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
##  <a name="getdata"></a>  CAtlFileMappingBase::GetData  
 このメソッドを呼び出してファイル マップ オブジェクトからデータを取得します。  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 データへのポインターを返します。  
  
##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle  
 このメソッドを呼び出してファイル マッピング オブジェクトへのハンドルを返します。  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>戻り値  
 ファイル マッピング オブジェクトへのハンドルを返します。  
  
##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize  
 ファイル マッピング オブジェクトからマッピングのサイズを取得するには、このメソッドを呼び出します。  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>戻り値  
 マッピングのサイズを返します。  
  
### <a name="example"></a>例  
 例を参照して[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)です。  
  
##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile  
 開くか、指定したファイルのファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 マッピング オブジェクトの作成元のファイルへのハンドルします。 `hFile` 有効にする必要があるあり、INVALID_HANDLE_VALUE に設定することはできません。  
  
 `nMappingSize`  
 マッピングのサイズ。 識別されるファイルの現在のサイズをファイル マッピング オブジェクトの最大サイズは 0 の場合、 *hFile です。*  
  
 `nOffset`  
 マッピングの開始ファイルのオフセット。 オフセットの値は、システムのメモリ割り当ての粒度の倍数である必要があります。  
  
 `dwMappingProtection`  
 ファイルがマップされている場合、ファイルのビューに必要な保護。 参照してください`flProtect`で[CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) Windows SDK にします。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、そのため、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 ファイルのサイズが、ファイル マッピング オブジェクトのサイズを超えないファイル マッピング オブジェクトが作成された後場合は、すべてのファイルの内容を共有するために使用されます。 詳細については、次を参照してください。 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)と[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 例を参照して[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)です。  
  
##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem  
 すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nMappingSize`  
 マッピングのサイズ。 によって識別されるファイル マッピング オブジェクトの現在のサイズをファイル マッピング オブジェクトの最大サイズは 0 の場合、 `szName.`  
  
 `szName`  
 マッピング オブジェクトの名前。  
  
 *pbAlreadyExisted*  
 設定されている場合は TRUE、マッピング オブジェクト既に BOOL 値へのポインターが存在しています。  
  
 `lpsa`  
 ポインター、 **SECURITY_ATTRIBUTES**返されたハンドルを子プロセスが継承できるかどうかを決定する構造体。 参照してください*lpAttributes*で[CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) Windows SDK に含まれています。  
  
 `dwMappingProtection`  
 ファイルがマップされている場合、ファイルの表示に必要な保護。 参照してください`flProtect`で**CreateFileMapping** Windows SDK にします。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、そのため、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 **MapShareMem**によって作成された既存のファイル マッピング オブジェクトは、 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)プロセス間で共有します。  
  
##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping  
 指定したファイルの名前付きファイル マッピング オブジェクトを開くには、このメソッドを呼び出します。  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szName`  
 マッピング オブジェクトの名前。 この名前のファイル マッピング オブジェクトの開いているハンドルがあるし、マッピング オブジェクトのセキュリティ記述子と競合していない場合、`dwViewDesiredAccess`パラメーター、オープン操作は成功します。  
  
 `nMappingSize`  
 マッピングのサイズ。 によって識別されるファイル マッピング オブジェクトの現在のサイズをファイル マッピング オブジェクトの最大サイズは 0 の場合、 `szName.`  
  
 `nOffset`  
 マッピングの開始ファイルのオフセット。 オフセットの値は、システムのメモリ割り当ての粒度の倍数である必要があります。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、そのため、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、入力パラメーターが有効でない場合、アサーション エラーが発生します。  
  
##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =  
 現在のファイル マッピング オブジェクトを別のファイル マッピング オブジェクトに設定します。  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 現在のファイル マッピング オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトへの参照を返します。  
  
##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap  
 ファイル マッピング オブジェクトをマップ解除するには、このメソッドを呼び出します。  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します`S_OK`成功した場合、またはエラー`HRESULT`エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 参照してください[UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882)詳細については、Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CAtlFileMapping クラス](../../atl/reference/catlfilemapping-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
