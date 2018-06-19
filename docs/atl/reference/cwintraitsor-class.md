---
title: CWinTraitsOR クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR
- ATLWIN/ATL::CWinTraitsOR::GetWndExStyle
- ATLWIN/ATL::CWinTraitsOR::GetWndStyle
dev_langs:
- C++
helpviewer_keywords:
- CWinTraitsOR class
- window styles, default values for ATL
ms.assetid: 1eb7b1e8-a9bd-411b-a30a-35a8a10af989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3df5081d8584d821737350176740b6fd067ac78f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361461"
---
# <a name="cwintraitsor-class"></a>CWinTraitsOR クラス
このクラスは、window オブジェクトを作成するときに使用するスタイルを標準化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <DWORD t_dwStyle = 0,
          DWORD t_dwExStyle = 0, 
          class TWinTraits = CControlWinTraits>
class CWinTraitsOR
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_dwStyle`  
 既定のウィンドウ スタイル。  
  
 `t_dwExStyle`  
 既定の拡張ウィンドウ スタイル。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinTraitsOR::GetWndExStyle](#getwndexstyle)|拡張スタイルを取得、`CWinTraitsOR`オブジェクト。|  
|[CWinTraitsOR::GetWndStyle](#getwndstyle)|標準のスタイルを取得、`CWinTraitsOR`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 これは、[ウィンドウの特徴](../../atl/understanding-window-traits.md)クラスには、ATL ウィンドウ オブジェクトを作成するために使用するスタイルを標準化するための簡単な方法が用意されています。 テンプレート パラメーターとしてこのクラスの特殊化を使用して[CWindowImpl](../../atl/reference/cwindowimpl-class.md)または別に使用される標準および拡張スタイルの最小セットを指定する、ATL のウィンドウ クラスのウィンドウ クラスのインスタンス。  
  
 特定のスタイルが設定されているウィンドウ クラスのすべてのインスタンスの他のスタイルを許容しつつへの呼び出しで、インスタンスごとに設定することを確認する場合は、このテンプレートの特殊化を使用して[CWindowImpl::Create](../../atl/reference/cwindowimpl-class.md#create)です。  
  
 既定の呼び出しでは、他のスタイルが指定されていない場合にのみ使用されるウィンドウ スタイルを指定する場合は、`CWindowImpl::Create`を使用して[CWinTraits](../../atl/reference/cwintraits-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="getwndstyle"></a>  CWinTraitsOR::GetWndStyle  
 (論理 OR 演算子を使用して) の標準的なスタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトとで指定された既定のスタイル`t_dwStyle`です。  
  
```
static DWORD GetWndStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ウィンドウの作成に使用されるスタイルです。  
  
### <a name="return-value"></a>戻り値  
 渡されたスタイルの組み合わせ`dwStyle`と既定値で指定されたもの`t_dwStyle`、論理 OR 演算子を使用します。  
  
##  <a name="getwndexstyle"></a>  CWinTraitsOR::GetWndExStyle  
 (論理 OR 演算子を使用して) の拡張スタイルの組み合わせを取得するには、この関数を呼び出して、`CWinTraits`オブジェクトとで指定された既定のスタイル`t_dwStyle`です。  
  
```
static DWORD GetWndExStyle(DWORD dwExStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 拡張スタイルのウィンドウの作成に使用します。  
  
### <a name="return-value"></a>戻り値  
 渡される拡張スタイルの組み合わせ`dwExStyle`であり、既定で指定されたもの`t_dwExStyle`、論理 OR 演算子を使用します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴を理解する](../../atl/understanding-window-traits.md)

