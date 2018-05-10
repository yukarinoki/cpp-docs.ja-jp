---
title: Concurrency::graphics::direct3d Namespace |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d
- amp_short_vectors/Concurrency::graphics::direct3d
dev_langs:
- C++
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6835297ca3248fcae92d94d98ab5620f86b5ba58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrencygraphicsdirect3d-namespace"></a>Concurrency::graphics::direct3d 名前空間
提供、 [get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)と[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)メソッドです。  
  
## <a name="syntax"></a>構文  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="functions"></a>関数  
  
|名前<br /><br /> 説明|  
|--------------------------|  
|[get_sampler](concurrency-graphics-direct3d-namespace-functions.md#get_sampler)<br /><br /> 指定されたサンプラー オブジェクトを表す特定のアクセラレータ ビューについて、Direct3D サンプラーの状態インターフェイスを取得します。|  
|[get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)<br /><br /> 指定した基になる Direct3D テクスチャ インターフェイスを取得[テクスチャ](texture-class.md)オブジェクト。|  
|[make_sampler](concurrency-graphics-direct3d-namespace-functions.md#make_sampler)<br /><br /> Direct3D サンプラーの状態インターフェイス ポインターからサンプラーを作成します。|  
|[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)<br /><br /> 作成、[テクスチャ](texture-class.md)指定されたパラメーターを使用してオブジェクト。|  
|[msad4](concurrency-graphics-direct3d-namespace-functions.md#msad4)<br /><br /> 4 バイトの参照値と 8 バイトのソース値を比較し、4 個の合計値のベクターを累積します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
