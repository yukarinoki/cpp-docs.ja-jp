---
title: Platform::array クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6a326db5400d8dfb335f9c9e20867a26db59b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformarray-class"></a>Platform::Array クラス
アプリケーション バイナリ インターフェイス (ABI) を越えて受け渡しでき、変更もできる 1 次元配列を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp    
template <typename T>  
private ref class Array<TArg, 1> :   
    public WriteOnlyArray<TArg, 1>,  
    public IBoxArray<TArg>   
```  
  
### <a name="members"></a>メンバー  
 Platform::array からすべてのメソッドの継承[platform::writeonlyarray クラス](../cppcx/platform-writeonlyarray-class.md)を実装し、`Value`のプロパティ、 [platform::iboxarray インターフェイス](../cppcx/platform-iboxarray-interface.md)です。  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Array コンストラクター](#ctor)|クラス テンプレート パラメーターによって指定された型の変更可能な 1 次元配列を初期化します*T*です。|  
  
### <a name="methods"></a>メソッド  
 参照してください[platform::writeonlyarray クラス](../cppcx/platform-writeonlyarray-class.md)です。  
  
### <a name="properties"></a>プロパティ  
  
|||  
|-|-|  
|[Array::value](#value)|現在の配列へのハンドルを取得します。|  
  
### <a name="remarks"></a>コメント  
 この Array クラスはシール クラスであり、継承できません。  
  
 Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていませんし、そのため、IVector を渡すことはできません < platform::array\<T >> 戻り値またはメソッド パラメーターとして。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。  
  
 Platform::array を使用するタイミングと方法の詳細については、次を参照してください。 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)です。  
  
 Windows ランタイムの型システムは、ジャグ配列の概念をサポートしていませんし、そのため、IVector を渡すことはできません < platform::array\<T >> 戻り値またはメソッド パラメーターとして。 ABI を通じてジャグ配列またはシーケンスのシーケンスを渡すには、 `IVector<IVector<T>^>`を使用します。  
  
 このクラスは、コンパイラによって自動的に含まれる vccorlib.h ヘッダーで定義されます。 これは platform.winmd で定義されているパブリック型ではないため、Intellisense では表示されますが、オブジェクト ブラウザーでは表示されません。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  

 
## <a name="ctor"></a>  Array コンス トラクター
クラス テンプレート パラメーターによって指定された型の変更可能な 1 次元配列を初期化します*T*です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Array(unsigned int size);  
Array(T* data, unsigned int size);    
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 クラス テンプレート パラメーター。  
  
 `size`  
 配列の要素数。  
  
 `data`  
 この Array オブジェクトを初期化するために使用する型 `T` のデータ配列へのポインター。  
  
### <a name="remarks"></a>コメント  
 Platform::array のインスタンスを作成する方法の詳細については、次を参照してください。 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)です。

## <a name="get"></a>  Array::get メソッド
指定されたインデックス位置にある配列要素への参照を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp    
T& get(unsigned int index)  const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `index`  
 配列の要素を識別する 0 から始まるインデックス。 最小インデックスは 0、最大のインデックスによって指定された値、`size`内のパラメーター、[配列コンス トラクター](#ctor)です。  
  
### <a name="return-value"></a>戻り値  
 `index` パラメーターで指定された配列要素。  
  
## <a name="value"></a>  Array::value プロパティ
現在の配列へのハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp 
property Array^ Value;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の配列へのハンドル。  

## <a name="see-also"></a>関連項目  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)   
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)