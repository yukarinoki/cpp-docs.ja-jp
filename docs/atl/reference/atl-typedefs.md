---
title: ATL Typedef |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcore/ATL::_ATL_BASE_MODULE
- atlbase/ATL::_ATL_COM_MODULE
- atlbase/ATL::_ATL_MODULE
- atlbase/ATL::_ATL_WIN_MODULE
- atlutil/ATL::ATL_URL_PORT
- atlbase/ATL::CComDispatchDriver
- atlbase/ATL::CComGlobalsThreadModel
- atlbase/ATL::CComObjectThreadModel
- atlwin/ATL::CContainedWindow
- atlpath/ATL::CPath
- atlpath/ATL::CPathA
- atlpath/ATL::CPathW
- " atlsimpcoll/ATL::CSimpleValArray"
- " atlutil/ATL::LPCURL"
- atlbase/ATL::DefaultThreadTraits
- atlutil/ATL::LPURL
dev_langs:
- C++
helpviewer_keywords:
- typedefs, ATL
- typedefs
- ATL, typedefs
ms.assetid: 7dd05baa-3efb-4e3b-af23-793c610f4560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 811dbda4360bcb3a618a4ceaa5228e57dab312ae
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34283328"
---
# <a name="atl-typedefs"></a>ATL Typedef
Active Template Library には、次の typedef が含まれています。  
  
|||  
|-|-|  
|[_ATL_BASE_MODULE](#_atl_base_module)|基づく typedef として定義されている[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)です。|  
|[_ATL_COM_MODULE](#_atl_com_module)|基づく typedef として定義されている[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)です。|  
|[_ATL_MODULE](#_atl_module)|基づく typedef として定義されている[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)です。|  
|[_ATL_WIN_MODULE](#_atl_win_module)|基づく typedef として定義されている[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|  
|[ATL_URL_PORT](#atl_url_port)|によって使用される種類[CUrl](../../atl/reference/curl-class.md)のポート番号を指定します。|  
|[CComDispatchDriver](#ccomdispatchdriver)|このクラスは、COM インターフェイス ポインターを管理します。|  
|[CComGlobalsThreadModel](#ccomglobalsthreadmodel)|適切なスレッドに使用されているスレッドのモデルに関係なく、モデルのメソッドを呼び出します。|  
|[CComObjectThreadModel](#ccomobjectthreadmodel)|適切なスレッドに使用されているスレッドのモデルに関係なく、モデルのメソッドを呼び出します。|  
|[CContainedWindow](#ccontainedwindow)|このクラスは、特殊化した**CContainedWindowT です。**|  
|[CPath](#cpath)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CString`です。|  
|[CPathA](#cpatha)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringA`です。|  
|[CPathW](#cpathw)|特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringW`です。|  
|[CSimpleValArray](#csimplevalarray)|単純型を格納する配列を表します。|  
|[DefaultThreadTraits](#defaultthreadtraits)|既定のスレッドの特徴 (traits) クラス。|  
|[LPCURL](#lpcurl)|定数へのポインター [CUrl](../../atl/reference/curl-class.md)オブジェクト。|  
|[LPURL](#lpurl)|ポインター、 [CUrl](../../atl/reference/curl-class.md)オブジェクト。|  
  
##  <a name="_atl_base_module"></a>  _ATL_BASE_MODULE  
 _ATL_BASE_MODULE70 に基づいて typedef として定義されます。  
  
```   
typedef ATL::_ATL_BASE_MODULE70 _ATL_BASE_MODULE;   
```  
  
### <a name="remarks"></a>コメント  
 すべての ATL プロジェクトで使用されます。 基づく[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)です。  
  
 ATL 7.0 モジュール クラスの一部であるクラスは、_ATL_BASE_MODULE 構造体から派生します。  ATL モジュール クラスの詳細についてを参照してください[COM モジュール クラス](../../atl/com-modules-classes.md)です。  

## <a name="requirements"></a>要件
**ヘッダー:** atlcore.h

##  <a name="_atl_com_module"></a>  _ATL_COM_MODULE  
 _ATL_COM_MODULE70 に基づいて typedef として定義されます。  
  
```   
typedef ATL::_ATL_COM_MODULE70 _ATL_COM_MODULE;   
```  
  
### <a name="remarks"></a>コメント  
 COM 機能を使用する ATL プロジェクトによって使用されます。 基づく[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)です。  

## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h
  
##  <a name="_atl_module"></a>  _ATL_MODULE  
 _ATL_MODULE70 に基づいて typedef として定義されます。  
  
```   
typedef ATL::_ATL_MODULE70 _ATL_MODULE;   
```  
## <a name="requirements"></a>要件
**ヘッダー:** 
  
### <a name="remarks"></a>コメント  
 基づく[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)です。  
  
##  <a name="_atl_win_module"></a>  _ATL_WIN_MODULE  
 _ATL_WIN_MODULE70 に基づいて typedef として定義されます。  
  
```   
typedef ATL::_ATL_WIN_MODULE70 _ATL_WIN_MODULE; 
 
```  
  
### <a name="remarks"></a>コメント  
 Windowing 機能を使用する ATL プロジェクトによって使用されます。 基づく[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)です。  

## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h 
  
##  <a name="atl_url_port"></a>  ATL_URL_PORT 
  によって使用される種類[CUrl](curl-class.md)のポート番号を指定します。
```  
typedef WORD ATL_URL_PORT;
```  

## <a name="requirements"></a>要件
**ヘッダー:** atlutil.h

##  <a name="ccomdispatchdriver"></a>  CComDispatchDriver  
 このクラスは、COM インターフェイス ポインターを管理します。  
  
```   
typedef CComQIPtr<IDispatch, &__uuidof(IDispatch)> CComDispatchDriver;   
```  
## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h
  
##  <a name="ccomglobalsthreadmodel"></a>  CComGlobalsThreadModel  
 適切なスレッドに使用されているスレッドのモデルに関係なく、モデルのメソッドを呼び出します。  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComGlobalsThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>コメント  
 モデルによっては、スレッド処理、アプリケーションで使用される、`typedef`名前`CComGlobalsThreadModel`いずれかを参照して[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)です。 これらのクラスを追加指定`typedef`クリティカル セクション クラスを参照する名前。  
  
> [!NOTE]
> `CComGlobalsThreadModel` クラスを参照していません[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)です。  
  
 使用して`CComGlobalsThreadModel`特定のスレッド処理モデル クラスを指定することから解放します。 使用されている、スレッディング モデルに関係なく、適切なメソッドが呼び出されます。  
  
 加え`CComGlobalsThreadModel`、ATL には、`typedef`名前[CComObjectThreadModel](#ccomobjectthreadmodel)です。 各によって参照されるクラス`typedef`次の表に示すように使用される、スレッド処理モデルによって異なります。  
  
|Typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S =`CComSingleThreadModel`です。M = `CComMultiThreadModel`  
  
 使用して`CComObjectThreadModel`を 1 つのオブジェクト クラス内で。 使用して`CComGlobalsThreadModel`または複数のスレッドでモジュールのリソースを保護する場合、プログラムにグローバルに使用できるオブジェクト。  

## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h
  
##  <a name="ccomobjectthreadmodel"></a>  CComObjectThreadModel  
 適切なスレッドに使用されているスレッドのモデルに関係なく、モデルのメソッドを呼び出します。  
  
```   
#if defined(_ATL_SINGLE_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_APARTMENT_THREADED)  
typedef CComSingleThreadModel CComObjectThreadModel;  
#elif defined(_ATL_FREE_THREADED)  
typedef CComMultiThreadModel CComObjectThreadModel;  
#else  
#pragma message ("No global threading model defined")  
#endif   
```  
  
### <a name="remarks"></a>コメント  
 モデルによっては、スレッド処理、アプリケーションで使用される、`typedef`名前`CComObjectThreadModel`いずれかを参照して[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)です。 これらのクラスを追加指定`typedef`クリティカル セクション クラスを参照する名前。  
  
> [!NOTE]
> `CComObjectThreadModel` クラスを参照していません[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)です。  
  
 使用して`CComObjectThreadModel`特定のスレッド処理モデル クラスを指定することから解放します。 使用されている、スレッディング モデルに関係なく、適切なメソッドが呼び出されます。  
  
 加え`CComObjectThreadModel`、ATL には、`typedef`名前[CComGlobalsThreadModel](#ccomglobalsthreadmodel)です。 各によって参照されるクラス`typedef`次の表に示すように使用される、スレッド処理モデルによって異なります。  
  
|Typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S =`CComSingleThreadModel`です。M = `CComMultiThreadModel`  
  
 使用して`CComObjectThreadModel`を 1 つのオブジェクト クラス内で。 使用して`CComGlobalsThreadModel`でいずれかであるオブジェクトをプログラム、または複数のスレッドでモジュールのリソースを保護するときにグローバルに使用できます。  

## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h
  
##  <a name="ccontainedwindow"></a>  CContainedWindow  
 このクラスは、特殊化した**CContainedWindowT です。**  
  
```   
typedef CContainedWindowT<CWindow> CContainedWindow;   
```  

## <a name="requirements"></a>要件
**ヘッダー:** atlwin.h
  
### <a name="remarks"></a>コメント  
 `CContainedWindow` 特殊化[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)です。 基底クラスまたは特徴 (traits) を変更する場合を使用して`CContainedWindowT`直接です。  
  
##  <a name="cpath"></a>  CPath  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CString`です。  
  
```   
typedef CPathT<CString> CPath;   
```  

## <a name="requirements"></a>要件
**ヘッダー:** atlpath.h
  
##  <a name="cpatha"></a>  CPathA  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringA`です。  
  
```   
typedef CPathT<CStringA> CPathA;   
```

## <a name="requirements"></a>要件
**ヘッダー:** atlpath.h  
  
##  <a name="cpathw"></a>  CPathW  
 特殊化した[CPathT](../../atl/reference/cpatht-class.md)を使用して`CStringW`です。  
  
```   
typedef ATL::CPathT<CStringW> CPathW;   
```  
## <a name="requirements"></a>要件
**ヘッダー:** atlpath.h
  
##  <a name="csimplevalarray"></a>  CSimpleValArray  
 単純型を格納する配列を表します。  
  
```   
#define CSimpleValArray CSimpleArray   
```  

  
### <a name="remarks"></a>コメント  
 `CSimpleValArray` 作成および単純なデータ型を含む配列を管理するために提供されます。 単純な #include の define [CSimpleArray](../../atl/reference/csimplearray-class.md)です。  


## <a name="requirements"></a>要件
**ヘッダー:** atlsimpcoll.h
  
##  <a name="lpcurl"></a>  LPCURL  
 定数へのポインター [CUrl](../../atl/reference/curl-class.md)オブジェクト。  
  
```   
typedef const CUrl* LPCURL;   
```  

## <a name="requirements"></a>要件
**ヘッダー:** atlutil.h

##  <a name="defaultthreadtraits"></a>  DefaultThreadTraits
既定のスレッドの特徴 (traits) クラス。

### <a name="syntax"></a>構文
```  
      #if defined(_MT)  
   typedef CRTThreadTraits DefaultThreadTraits;  
#else  
   typedef Win32ThreadTraits DefaultThreadTraits;  
#endif  
```

## <a name="remarks"></a>コメント
現在のプロジェクトでは、マルチ スレッド CRT を使用する場合は、DefaultThreadTraits が CRTThreadTraits として定義されます。 それ以外の場合、Win32ThreadTraits が使用されます。


## <a name="requirements"></a>要件
**ヘッダー:** atlbase.h
  
##  <a name="lpurl"></a>  LPURL  
 ポインター、 [CUrl](../../atl/reference/curl-class.md)オブジェクト。  
  
```   
typedef CUrl* LPURL;   
```  

## <a name="requirements"></a>要件
**ヘッダー:** atlutil.h


## <a name="see-also"></a>関連項目  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   
 [関数](../../atl/reference/atl-functions.md)   
 [グローバル変数](../../atl/reference/atl-global-variables.md)   
 [クラスと構造体](../../atl/reference/atl-classes.md)[マクロ](../../atl/reference/atl-macros.md)   
