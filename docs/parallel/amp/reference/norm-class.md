---
title: norm クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs:
- C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f23ea5d40ecca7ee47d7eae659bfd3da286d8831
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705394"
---
# <a name="norm-class"></a>norm クラス
Norm 数を表します。 各要素は、浮動小数点の数値の範囲内で [-1.0f、1.0 f]。  
  
## <a name="syntax"></a>構文  
  
```  
class norm;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[norm コンス トラクター](#ctor)|オーバーロードされます。 既定のコンストラクター 0.0f を初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|norm::operator-||  
|norm::operator--||  
|norm::operator float|変換演算子です。 Norm 数、浮動小数点に変換する値をポイントします。|  
|norm::operator*=||  
|norm::operator/=||  
|+ + norm::operator||  
|norm::operator+=||  
|norm::operator=||  
|norm::operator-=||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `norm`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp_short_vectors.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="ctor"></a> norm 

 既定のコンストラクター 0.0f を初期化します。  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `_V`  
 初期化するために使用する値。  
  
 `_Other`  
 初期化するために使用するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
