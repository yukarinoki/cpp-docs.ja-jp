---
title: IDocHostUIHandlerDispatch インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07d6d861bfa4a41d7d9ee6697dd72cba0da2ceda
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364246"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch インターフェイス
Microsoft の HTML の解析およびレンダリング エンジンへのインターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
> [!NOTE]
>  次の表のリンクが、INet SDK リファレンス トピックへのメンバーには、 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)インターフェイスです。 `IDocHostUIHandlerDispatch` 同じ機能を持つ**IDocUIHostHandler**、違いを`IDocHostUIHandlerDispatch`ディスパッチ インターフェイスに対しです**IDocUIHostHandler**カスタム インターフェイスです。  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML の実装から呼び出されます[IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115)です。 MSHTML がモーダルの UI を表示するときとも呼ばれます。|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|ホストが MSHTML のデータ オブジェクトを交換できるようにするために MSHTML によってホストに対して呼び出されます。|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|代替ホストを許可する、ドロップ先として使用されているときに、MSHTML によって呼び出されます[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)です。|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|ホストの IDispatch インターフェイスを取得するために MSHTML によって呼び出されます。|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML ホストの UI 機能を取得します。|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|MSHTML がユーザー設定を格納するレジストリ キーを返します。|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|MSHTML がメニューやツールバーを削除するときに呼び出されます。|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML の実装から呼び出されます[ioleinplaceactiveobject::ondocwindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)です。|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML の実装から呼び出されます[ioleinplaceactiveobject::onframewindowactivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)です。|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML の実装から呼び出されます[ioleinplaceactiveobject:](http://msdn.microsoft.com/library/windows/desktop/ms680053)です。|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|コンテキスト メニューを表示するために MSHTML から呼び出されます。|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|により、ホストは MSHTML メニューとツールバーを置換します。|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|MSHTML によって呼び出されるときに[ioleinplaceactiveobject::translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360)または[iolecontrolsite::translateaccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756)と呼びます。|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|ホストに読み込まれる URL を変更することを許可する MSHTML によって呼び出されます。|  
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|コマンドの状態が変化したことをホストに通知します。|  
  
## <a name="remarks"></a>コメント  
 ホストは、メニューのツールバー、およびこのインターフェイスを実装することによって Microsoft HTML の解析およびレンダリング エンジン (MSHTML) によって使用されるコンテキスト メニューに置き換えることができます。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のように idl ファイルまたは C++ として使用できます。  
  
|定義の型|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
## <a name="see-also"></a>関連項目  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)









