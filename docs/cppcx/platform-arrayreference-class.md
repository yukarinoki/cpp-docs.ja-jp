---
title: Platform::arrayreference クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
dev_langs:
- C++
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8e4183c400cf45a23f24a98292b68f6df537da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference クラス
`ArrayReference` は、C スタイル配列に入力データを格納するときに、入力パラメーターの [Platform::Array^](../cppcx/platform-array-class.md) と置き換えることができる最適化の種類です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class ArrayReference  
```
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ArrayReference::ArrayReference](#ctor)|`ArrayReference` クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ArrayReference::operator() 演算子](#operator-call)|この `ArrayReference` を `Platform::Array<T>^*`に変換します。|  
|[ArrayReference::operator= 演算子](#operator-assign)|このインスタンスに別の `ArrayReference` の内容を割り当てます。|  
  
## <a name="exceptions"></a>例外  
  
### <a name="remarks"></a>コメント  
 `ArrayReference` を使用して C スタイル配列にデータを格納する方法であれば、一度 `Platform::Array` 変数にコピーしたうえで改めて C スタイル配列にコピーするような余分な操作が不要になります。 `ArrayReference`を使用した場合には、コピー操作が 1 回のみとなります。 コード例は、次を参照してください。 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)です。  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## <a name="ctor"></a>  Arrayreference::arrayreference コンス トラクター
新しいインスタンスを初期化、 [platform::arrayreference](../cppcx/platform-arrayreference-class.md)クラスです。  
  
### <a name="syntax"></a>構文  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
### <a name="parameters"></a>パラメーター  
 `dataArg`  
 配列データへのポインター。  
  
 `sizeArg`  
 ソース配列の要素数。  
  
 `otherArg`  
 新しいインスタンスを初期化するためにデータが移動される `ArrayReference` オブジェクト。  
  
### <a name="remarks"></a>コメント  
  


## <a name="operator-assign"></a>  Arrayreference::operator = 演算子
現在指定されたオブジェクトを割り当てます[platform::arrayreference](../cppcx/platform-arrayreference-class.md)移動セマンティクスを使用してオブジェクト。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& otherArg);  
  
```  
  
### <a name="parameters"></a>パラメーター  
 `otherArg`  
 現在の `ArrayReference` オブジェクトに移動されたオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `ArrayReference` 型のオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 `Platform::ArrayReference` は、ref クラスではなく、標準 C++ クラス テンプレートです。  
  


## <a name="operator-call"></a>  Arrayreference::operator() 演算子
現在の変換[platform::arrayreference](../cppcx/platform-arrayreference-class.md)にオブジェクト、 [platform::array](../cppcx/platform-array-class.md)クラスです。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
Array<TArg>^ operator ();  
  
```  
  
### <a name="return-value"></a>戻り値  
 `Array<TArg>^` 型のオブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 [Platform::arrayreference](../cppcx/platform-arrayreference-class.md)と[platform::array](../cppcx/platform-array-class.md) 、標準 C++ クラス テンプレートいない ref クラスは、します。  
  


  
  
## <a name="see-also"></a>関連項目  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)