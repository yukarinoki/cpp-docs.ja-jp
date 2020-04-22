---
title: クラスを指定します。
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 16eebfff4330a47888d1b60eaa993ee87d120f72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748300"
---
# <a name="catlfilemappingbase-class"></a>クラスを指定します。

このクラスは、メモリ マップト ファイルを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlFileMappingBase
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイルマッピングベース::カトルファイルマッピングベース](#catlfilemappingbase)|コンストラクターです。|
|[ファイルマッピングベース:~カトルファイルマッピングベース](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カトルファイルマッピングベース::コピーから](#copyfrom)|ファイル マッピング オブジェクトからコピーします。|
|[ファイルマッピングベース::取得データ](#getdata)|ファイル マッピング オブジェクトからデータを取得します。|
|[ファイルマッピングベース::GetHandle](#gethandle)|ファイル ハンドルを返します。|
|[ファイルマッピングベース::ゲットマッピングサイズ](#getmappingsize)|ファイル マッピング オブジェクトからマッピング サイズを取得します。|
|[ファイルマッピングベース::マップファイル](#mapfile)|ファイル マッピング オブジェクトを作成します。|
|[カトルファイルマッピングベース::マップシェアメーム](#mapsharedmem)|すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成します。|
|[ファイルマッピングベース::オープンマッピング](#openmapping)|ファイル マッピング オブジェクトへのハンドルを返します。|
|[ファイルマッピングベース::マップ解除](#unmap)|ファイル マッピング オブジェクトのマップを解除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[カトルファイルマッピングベース::演算子 =](#operator_eq)|現在のファイル マッピング オブジェクトを別のファイル マップ オブジェクトに設定します。|

## <a name="remarks"></a>解説

ファイル マッピングとは、ファイルの内容とプロセスの仮想アドレス空間の一部の関連付けです。 このクラスは、プログラムが簡単にデータにアクセスして共有できるようにするファイル マッピング オブジェクトを作成するためのメソッドを提供します。

詳細については、Windows SDK[の「ファイル マッピング](/windows/win32/Memory/file-mapping)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlfile.h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>ファイルマッピングベース::カトルファイルマッピングベース

コンストラクターです。

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>パラメーター

*Orig*<br/>
新しいオブジェクトを作成するためにコピーする元のファイル マッピング オブジェクト。

### <a name="remarks"></a>解説

既存のオブジェクトを使用して、必要に応じて新しいファイル マッピング オブジェクトを作成します。 特定のファイルのファイル マッピング オブジェクトを開いたり作成したりするには[、CAtlFileMappingBase::MapFile](#mapfile)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>ファイルマッピングベース:~カトルファイルマッピングベース

デストラクターです。

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>解説

クラスによって割り当てられたリソースを解放し[、CAtlFileMappingBase::Unmap](#unmap)メソッドを呼び出します。

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>カトルファイルマッピングベース::コピーから

ファイル マッピング オブジェクトからコピーします。

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>パラメーター

*Orig*<br/>
コピー元の元のファイル マッピング オブジェクト。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>ファイルマッピングベース::取得データ

ファイル マッピング オブジェクトからデータを取得します。

```cpp
void* GetData() const throw();
```

### <a name="return-value"></a>戻り値

データへのポインターを返します。

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>ファイルマッピングベース::GetHandle

ファイル マッピング オブジェクトへのハンドルを返します。

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>戻り値

ファイル マッピング オブジェクトへのハンドルを返します。

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>ファイルマッピングベース::ゲットマッピングサイズ

ファイル マッピング オブジェクトからマッピング サイズを取得します。

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>戻り値

マッピング サイズを返します。

### <a name="example"></a>例

[の例を](#catlfilemappingbase)参照してください。

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>ファイルマッピングベース::マップファイル

指定したファイルのファイル マッピング オブジェクトを開くか作成します。

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>パラメーター

*hファイル*<br/>
マッピング オブジェクトの作成元のファイルへのハンドル。 *hfile*は有効である必要があり、INVALID_HANDLE_VALUE に設定できません。

*サイズを指定します。*<br/>
マッピング サイズ。 0 の場合、ファイル・マッピング・オブジェクトの最大サイズは *、hFile*で識別されるファイルの現在のサイズと等しくなります。

*オフセット*<br/>
マッピングを開始するファイル オフセット。 オフセット値は、システムのメモリ割り当ての粒度の倍数である必要があります。

*デウマッピングプロテクション*<br/>
ファイルがマップされるときに、ファイル ビューに必要な保護。 Windows SDK[の「ファイル マッピングの作成](/windows/win32/api/winbase/nf-winbase-createfilemappinga)」の*flProtect*を参照してください。

*アクセスを許可します。*<br/>
ファイル ビューへのアクセスの種類、およびファイルによってマップされるページの保護を指定します。 Windows SDK の *「dwDesired アクセス*」[を](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex)参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ファイル マッピング オブジェクトを作成した後、ファイルのサイズがファイル マッピング オブジェクトのサイズを超えないようにする必要があります。ファイルが存在する場合、ファイルの内容の一部が共有に使用できるわけではありません。 詳細については、Windows SDK[の「ファイル マッピング](/windows/win32/api/winbase/nf-winbase-createfilemappinga)と[マップビューのファイルEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex)の作成」を参照してください。

### <a name="example"></a>例

[の例を](#catlfilemappingbase)参照してください。

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>カトルファイルマッピングベース::マップシェアメーム

すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成します。

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

*サイズを指定します。*<br/>
マッピング サイズ。 0 の場合、ファイル マッピング オブジェクトの最大サイズは *、szName*で識別されるファイル マッピング オブジェクトの現在のサイズと同じになります。

*Szname*<br/>
マッピング オブジェクトの名前。

*pb既に存在する*<br/>
マッピング オブジェクトが既に存在する場合に TRUE に設定されている BOOL 値へのポイント。

*lpsa*<br/>
返されたハンドルを`SECURITY_ATTRIBUTES`子プロセスに継承できるかどうかを示す構造体へのポインター。 Windows SDK の[「ファイル マッピングの作成](/windows/win32/api/winbase/nf-winbase-createfilemappinga)」の*lp 属性*を参照してください。

*デウマッピングプロテクション*<br/>
ファイルがマップされている場合の、ファイル ビューに必要な保護。 Windows SDK`CreateFileMapping`の *「での flProtect」* を参照してください。

*アクセスを許可します。*<br/>
ファイル ビューへのアクセスの種類、およびファイルによってマップされるページの保護を指定します。 Windows SDK の *「dwDesired アクセス*」[を](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex)参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

`MapShareMem`によって[作成](/windows/win32/api/winbase/nf-winbase-createfilemappinga)された既存のファイル マッピング オブジェクトをプロセス間で共有できます。

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>ファイルマッピングベース::オープンマッピング

指定したファイルの名前付きファイル マッピング オブジェクトを開きます。

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>パラメーター

*Szname*<br/>
マッピング オブジェクトの名前。 この名前でファイル マッピング オブジェクトへのオープン ハンドルがあり、マッピング オブジェクトのセキュリティ記述子が*dwViewDesiredAccess*パラメーターと競合しない場合は、開く操作が成功します。

*サイズを指定します。*<br/>
マッピング サイズ。 0 の場合、ファイル マッピング オブジェクトの最大サイズは *、szName*で識別されるファイル マッピング オブジェクトの現在のサイズと同じになります。

*オフセット*<br/>
マッピングを開始するファイル オフセット。 オフセット値は、システムのメモリ割り当ての粒度の倍数である必要があります。

*アクセスを許可します。*<br/>
ファイル ビューへのアクセスの種類、およびファイルによってマップされるページの保護を指定します。 Windows SDK の *「dwDesired アクセス*」[を](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex)参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、入力パラメーターが無効な場合にアサーション エラーが発生します。

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>カトルファイルマッピングベース::演算子 =

現在のファイル マッピング オブジェクトを別のファイル マップ オブジェクトに設定します。

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>パラメーター

*Orig*<br/>
現在のファイル マッピング オブジェクト。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照を返します。

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>ファイルマッピングベース::マップ解除

ファイル マッピング オブジェクトのマップを解除します。

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の「[マップの解除](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスを指定します。](../../atl/reference/catlfilemapping-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
