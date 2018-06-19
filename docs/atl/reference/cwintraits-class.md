---
title: CWinTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraits
- ATLWIN/ATL::CWinTraits
- ATLWIN/ATL::CWinTraits::GetWndExStyle
- ATLWIN/ATL::CWinTraits::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWinTraits class
- window styles, default values for ATL
- CWinTraits class
- CFrameWinTraits class
- CControlWinTraits class
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea1eafc6376c44a09d13fb513d41f222048708d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362509"
---
# <a name="cwintraits-class"></a>CWinTraits クラス
このクラスは、window オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <DWORD t_dwStyle = 0, DWORD t_dwExStyle = 0>  class CWinTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_dwStyle`  
 既定の標準的なウィンドウのスタイル。  
  
 `t_dwExStyle`  
 既定の拡張ウィンドウ スタイル。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinTraits::GetWndExStyle](#getwndexstyle)|(静的)拡張スタイルを取得、`CWinTraits`オブジェクト。|  
|[CWinTraits::GetWndStyle](#getwndstyle)|(静的)標準のスタイルを取得、`CWinTraits`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための簡単な方法が用意されています。 テンプレート パラメーターとしてこのクラスの特殊化を使用して[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または別のための既定の標準および拡張スタイルを指定する、ATL のウィンドウ クラスのウィンドウ クラスのインスタンス。  
  
 既定の呼び出しでは、他のスタイルが指定されていない場合にのみ使用されるウィンドウ スタイルを指定する場合は、このテンプレートを使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)です。  
  
 ATL には、ウィンドウ スタイルの一般的に使用される組み合わせのためには、このテンプレートの定義済み特殊化の 3 つが用意されています。  
  
 `CControlWinTraits`  
 標準コントロール ウィンドウの設計されています。 次の標準のスタイルを使用して: **WS_CHILD**、 **WS_VISIBLE**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**です。 拡張スタイルはありません。  
  
 `CFrameWinTraits`  
 標準のフレーム ウィンドウ用に設計されています。 使用される標準のスタイルが含まれます: **WS_OVERLAPPEDWINDOW**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**です。 使用されている拡張スタイルが含まれます: **WS_EX_APPWINDOW**と**WS_EX_WINDOWEDGE**です。  
  
 `CMDIChildWinTraits`  
 標準的な MDI 子ウィンドウの設計されています。 使用される標準のスタイルが含まれます: **WS_OVERLAPPEDWINDOW**、 **WS_CHILD**、 **WS_VISIBLE**、 **WS_CLIPCHILDREN**、および**WS_CLIPSIBLINGS**です。 使用されている拡張スタイルが含まれます: **WS_EX_MDICHILD**です。  
  
 特定のスタイルが設定されているインスタンスごとの単位で設定するには、他のスタイルを許容しつつ、ウィンドウ クラスのすべてのインスタンスを使用することを確認する場合は、 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="getwndstyle"></a>  CWinTraits::GetWndStyle  
 標準のスタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクト。  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 標準的なスタイルのウィンドウの作成に使用します。 場合`dwStyle`は 0、テンプレートのスタイル値 ( `t_dwStyle`) が返されます。 場合`dwStyle`がゼロ以外、`dwStyle`が返されます。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトの標準的なウィンドウのスタイルです。  
  
##  <a name="getwndexstyle"></a>  CWinTraits::GetWndExStyle  
 拡張スタイルを取得するには、この関数を呼び出して、`CWinTraits`オブジェクト。  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 拡張スタイルのウィンドウの作成に使用します。 場合`dwExStyle`は 0、テンプレートのスタイル値 ( `t_dwExStyle`) が返されます。 場合`dwExStyle`がゼロ以外、`dwExStyle`が返されます。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトの拡張ウィンドウ スタイル。  
  
## <a name="see-also"></a>関連項目  
 [クラスのメンバー](http://msdn.microsoft.com/en-us/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴を理解する](../../atl/understanding-window-traits.md)
