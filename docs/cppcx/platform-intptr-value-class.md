---
title: Platform::intptr 値クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs:
- C++
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a97d77f0b84366c83f09f6a6c72afe1bbb25dc6d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758831"
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr 値クラス
サイズがプラットフォームに特有の (32 ビットまたは 64 ビット)、符号付きポインターまたはハンドルを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>メンバー  
 IntPtr には、次のメンバーがあります。  
  
|メンバー|説明|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|IntPtr の新しいインスタンスを初期化します。|  
|[IntPtr::op_explicit 演算子](#op-explicit)|指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。|  
|[IntPtr::ToInt32](#toint32)|現在の IntPtr を 32 ビット整数に変換します。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされている最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  

## <a name="ctor"> </a> IntPtr::IntPtr コンストラクター
指定された値を持つ IntPtr の新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>パラメーター  
 値  
 64 ビットのハンドルまたはポインター、または 64 ビット値へのポインター、または 64 ビット値に変換できる 32 ビット値。  
  


## <a name="op-explicit"> </a> IntPtr::op_explicit 演算子
指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>パラメーター  
 value1  
 ハンドルまたは IntPtr へのポインター。  
  
 value2  
 IntPtr に変換できる 32 ビット整数。  
  
 value3  
 IntPtr。  
  
### <a name="return-value"></a>戻り値  
 1 番目と 2 番目の演算子は IntPtr を返します。 3 番目の演算子は、現在の IntPtr によって表される値へのポインターを返します。  
  


## <a name="toint32"> </a> Intptr::toint32 メソッド
現在の IntPtr 値を 32 ビット整数に変換します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>戻り値  
 32 ビット整数。  
  
  
## <a name="see-also"></a>関連項目  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)