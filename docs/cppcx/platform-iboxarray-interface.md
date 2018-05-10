---
title: Platform::iboxarray インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 572724dcebbdb3921b26d6c688ff5d68d1392437
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray インターフェイス
`IBoxArray` はアプリケーション バイナリ インターフェイス (ABI) を越えて渡されるか、XAML コントロールなどの `Platform::Object^` 要素のコレクションに格納される値型の配列のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 各配列要素のボックス化された値の型。  
  
### <a name="remarks"></a>コメント  
 `IBoxArray` C + + CX 名`Windows::Foundation::IReferenceArray`です。  
  
### <a name="members"></a>メンバー  
 `IBoxArray` インターフェイスは `IValueType` インターフェイスを継承します。 `IBoxArray` にも、次に示すメンバーがあります。  
  
|メソッド|説明|  
|------------|-----------------|  
|[値](#value)|以前にこの `IBoxArray` インスタンスに格納されていたことがあり、ボックス化が解除されている配列を返します。|  

## <a name="value"></a> Iboxarray::value プロパティ
このオブジェクトに元から格納されていた値を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
property T Value {T get();}  
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ボックス化された値の型。  
  
### <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 このオブジェクトに元から格納されていた値を返します。  
  
### <a name="remarks"></a>コメント  
 例については、次を参照してください。[ボックス化](../cppcx/boxing-c-cx.md)です。  
  
  
## <a name="see-also"></a>関連項目  
 [Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)