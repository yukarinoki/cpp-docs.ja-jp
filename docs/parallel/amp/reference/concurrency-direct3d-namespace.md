---
title: Concurrency::direct3d Namespace |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs:
- C++
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9516e3f89d393405a5f71af569a50e46e381d579
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d 名前空間
`direct3d` 名前空間は、D3D の相互運用性をサポートする関数を提供します。 これにより、AMP コードでの計算に D3D のリソースをシームレスに使用できるようになると共に、AMP で作成したリソースを D3D コードで使用することができ、冗長な中間コピーを作成する必要がありません。 C++ AMP を使用することによって、DirectX アプリケーションの計算中心のセクションの処理を加速し、AMP の計算から生成されるデータに対して D3D API を使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[scoped_d3d_access_lock クラス](scoped-d3d-access-lock-class.md)|`accelerator_view` オブジェクトの D3D アクセスのロックの RAII ラッパー。|  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[adopt_d3d_access_lock_t 構造体](adopt-d3d-access-lock-t-structure.md)|D3D のアクセスのロックを示すタグの種類は、取得するのではなく、導入する必要があります。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|引数の絶対値を返します。|  
|[clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|オーバーロードされます。 _X を指定された _Min と _Max の範囲にクランプします。|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|_X 内で設定されているビットの数をカウントします。|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|作成、 [accelerator_view クラス](accelerator-view-class.md)Direct3D デバイス インターフェイスへのポインターから|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|accelerator_view と共有されるリソースに対して安全に D3D 演算を実行する目的で、accelerator_view のロックを取得します。|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|ブロックせずに、accelerator_view に対する D3D アクセスのロックを取得します。|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|指定された accelerator_view に対する D3D アクセスのロックを解除します。|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|最上位ビットから下位に向かって操作して、_X 内で最初に設定されているビットの位置を取得します。|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|最下位ビットから上位に向かって操作して、_X 内で最初に設定されているビットの位置を取得します。|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|配列を基にする D3D バッファー インターフェイスを取得します。|  
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|2 つの値を比較し、大きい方の値を返します。|  
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|2 つの値を比較し、小さい方の値を返します。|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|指定された accelerator_view についてタイムアウトが無効であるかどうかを示すブール型のフラグを返します。|  
|[mad](concurrency-direct3d-namespace-functions-amp.md#mad)|オーバーロードされます。 3 個の引数に対して乗算/加算算術演算 (_X * _Y + _Z) を実行します。|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|D3D バッファーのインターフェイス ポインターから配列を作成します。|  
|[ノイズ](concurrency-direct3d-namespace-functions-amp.md#noise)|パーリン ノイズ アルゴリズムを使用して乱数値を生成します。|  
|[radians](concurrency-direct3d-namespace-functions-amp.md#radians)|_X を角度からラジアンに変換します。|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|引数の高速近似逆数を計算します。|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|_X 内のビットの順序を反転させます。|  
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|0 ～ 1 の範囲内で _X をクランプします。|  
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|オーバーロードされます。 引数の正弦を返します。|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|_X が [_Min, _Max] の範囲内にある場合、0 ～ 1 の滑らかなエルミート補間を返します。|  
|[step](concurrency-direct3d-namespace-functions-amp.md#step)|2 つの値を比較し、どちらの値が大きいかに応じて 0 または 1 を返します。|  
|[umax](concurrency-direct3d-namespace-functions-amp.md#umax)|2 つの符号なしの値を比較し、大きい方の値を返します。|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|2 つの符号なしの値を比較し、小さい方の値を返します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
