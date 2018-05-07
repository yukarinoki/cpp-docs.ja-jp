---
title: Platform::guid 値クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c295138d6239ce516b4f322fb5fc479e2235a6be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="platformguid-value-class"></a>Platform::Guid 値クラス
[GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) の種類を、Windows ランタイムの型システムで表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>メンバー  
 GUID には、 [Platform::Object Class](../cppcx/platform-object-class.md)から派生した Equals()、GetHashCode()、ToString()、GetTypeCode() メソッド、および [Platform::Type Class](../cppcx/platform-type-class.md). Guid には、次のメンバーもあります。  
  
|メンバー|説明|  
|------------|-----------------|  
|[Guid](#ctor)|Guid 構造体の新しいインスタンスを初期化します。|  
|[operator==](#operator-equality)|等値演算子。|  
|[operator!=](#operator-not-equal)|非等値演算子。|  
|[演算子 ()](#operator-call)|Guid を GUID に変換します。|  
  
### <a name="remarks"></a>コメント  
 Windows の関数 [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx)を使用して新しい Platform::Guid を作成する例については、「 [WinRT コンポーネント: GUID を作成する方法](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)」を参照してください。  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  

 
## <a name="ctor"></a> Guid::guid コンス トラクター
Guid 構造体の新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  );  
  
    Guid(GUID m);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n );  
```  
  
### <a name="parameters"></a>パラメーター  
 `a`  
 GUID の最初の 4 バイト。  
  
 `b`  
 GUID の次の 2 バイト。  
  
 `c`  
 GUID の次の 2 バイト。  
  
 `d`  
 GUID の次のバイト。  
  
 `e`  
 GUID の次のバイト。  
  
 `f`  
 GUID の次のバイト。  
  
 `g`  
 GUID の次のバイト。  
  
 `h`  
 GUID の次のバイト。  
  
 `i`  
 GUID の次のバイト。  
  
 `j`  
 GUID の次のバイト。  
  
 `k`  
 GUID の次のバイト。  
  
 `m`  
 定義されたとおりの GUID。  
  
 `n`  
 GUID の残りの 8 バイト。  
  

## <a name="operator-equality"></a> Guid::operator = = 演算子
2 つの guid を比較します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::Guid::operator==  
```  
  
### <a name="return-value"></a>戻り値  
 2 つの guid が等しい場合は true。

## <a name="operator-inequality"></a> Guid::operator! = 演算子
2 つの guid を比較します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::Guid::operator!=  
```  
  
### <a name="return-value"></a>戻り値  
 2 つの guid が等しくない場合は true。



## <a name="operator-call"></a> Guid::operator() 演算子
暗黙的に変換、 [GUID 構造体](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)platform::guid には GUID です。  
  
### <a name="syntax"></a>構文  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>戻り値  
 GUID 構造体。  
  
  
## <a name="see-also"></a>関連項目  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)