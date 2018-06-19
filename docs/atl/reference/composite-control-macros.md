---
title: 複合コントロール マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SINK_MAP
- atlcom/ATL::END_SINK_MAP
- atlcom/ATL::SINK_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- composite controls, macros
ms.assetid: 17f2dd5e-07e6-4aa6-b965-7a361c78c45e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61335d25b0d9b97fe1c7e9915aa9c3d8583eb854
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363662"
---
# <a name="composite-control-macros"></a>複合コントロール マクロ
これらのマクロは、イベント シンク マップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_SINK_MAP](#begin_sink_map)|複合コントロールのイベント シンク マップの先頭を示します。|  
|[END_SINK_MAP](#end_sink_map)|複合コントロールのイベント シンク マップの最後をマークします。|  
|[SINK_ENTRY](#sink_entry)|イベント シンク マップするエントリ。|  
|[SINK_ENTRY_EX](#sink_entry_ex)|追加のパラメーターを持つイベント シンク マップするエントリ。| 
|[SINK_ENTRY_EX_P](#sink_entry_ex)| (Visual Studio 2017)Iid へのポインターを受け取る点を除いて、SINK_ENTRY_EX 類似します。|  
|[SINK_ENTRY_INFO](#sink_entry_info)|使用するための手動で指定された型情報を持つイベント シンク マップ エントリ[されます](../../atl/reference/idispeventsimpleimpl-class.md)です。|  
|[SINK_ENTRY_INFO_P](#sink_entry_info)| (Visual Studio 2017)Iid へのポインターを受け取る点を除いて、SINK_ENTRY_INFO 類似します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  

##  <a name="begin_sink_map"></a>  BEGIN_SINK_MAP  
 複合コントロールのイベント シンク マップの先頭を宣言します。  
  
```
BEGIN_SINK_MAP(_class)
```  
  
### <a name="parameters"></a>パラメーター  
 `_class`  
 [in]コントロールを指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="end_sink_map"></a>  END_SINK_MAP  
 複合コントロールのイベント シンク マップの最後を宣言します。  
  
```
END_SINK_MAP()
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry"></a>  SINK_ENTRY  
 ハンドラー関数を宣言 ( `fn`) 指定されたイベントに対して ( `dispid`)、によって識別される、コントロールの`id`します。  
  
```
SINK_ENTRY( id, dispid, fn )
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]コントロールを識別します。  
  
 `dispid`  
 [in]指定したイベントを識別します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイル署名があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#104](../../atl/codesnippet/cpp/composite-control-macros_1.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry_ex"></a>  SINK_ENTRY_EX と SINK_ENTRY_EX_P
 ハンドラー関数を宣言 ( `fn`) 指定されたイベントに対して ( `dispid`)、ディスパッチ インターフェイスの ( *iid)* で指定されたコントロールの`id`します。  
  
```
SINK_ENTRY_EX( id, iid, dispid, fn )
SINK_ENTRY_EX_P( id, piid, dispid, fn ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]コントロールを識別します。  
  
 `iid`  
 [in]ディスパッチ インターフェイスを識別します。  

 `piid`  
 [in]ディスパッチ インターフェイスへのポインター。  
  
 `dispid`  
 [in]指定したイベントを識別します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイル署名があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#136](../../atl/codesnippet/cpp/composite-control-macros_2.h)]  
  
### <a name="remarks"></a>コメント  
 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  
##  <a name="sink_entry_info"></a>  SINK_ENTRY_INFO と SINK_ENTRY_INFO_P  
 使用して、`SINK_ENTRY_INFO`で必要な情報を提供するイベント シンク マップ内のマクロ[されます](../../atl/reference/idispeventsimpleimpl-class.md)関連するハンドラー関数にイベントをルーティングします。  
  
```
SINK_ENTRY_INFO( id, iid, dispid, fn, info )
SINK_ENTRY_INFO_P( id, piid, dispid, fn, info ) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]イベント ソースを識別する符号なし整数。 この値に一致する必要があります、 `nID` 、関連するテンプレート パラメーター[されます](../../atl/reference/idispeventsimpleimpl-class.md)基本クラスです。  
  
 `iid`  
 [in]ディスパッチ インターフェイスを識別する IID。  

 `piid`  
 [in]ディスパッチ インターフェイスを識別する IID へのポインター。
  
 `dispid`  
 [in]DISPID は指定されたイベントを識別します。  
  
 `fn`  
 [in]イベント ハンドラー関数の名前です。 この関数を使用する必要があります、 **_stdcall**呼び出し規約および適切なディスパッチ インターフェイス スタイル署名があります。  
  
 `info`  
 [in]イベント ハンドラー関数に関する情報を入力します。 この型情報がへのポインターの形で提供される、`_ATL_FUNC_INFO`構造体。 `CC_CDECL` Windows CE でサポートされる唯一のオプションは、`CALLCONV`のフィールド、`_ATL_FUNC_INFO`構造体。 その他の値はサポートされていないためその動作が定義されていません。  
  
### <a name="remarks"></a>コメント  
 最初の 4 つのマクロのパラメーターがの場合と同じ、 [SINK_ENTRY_EX](#sink_entry_ex)マクロです。 最後のパラメーターは、イベントの種類の情報を提供します。 ActiveX イベント シンクのみサポートしている戻り値の型 HRESULT または void、イベント ハンドラー メソッドからの CE ATL の実装その他の戻り値はサポートされていませんし、その動作は未定義です。  
  

## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [複合コントロールに関するグローバル関数](../../atl/reference/composite-control-global-functions.md)
