---
title: CSecurityAttributes クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47b0058cba19ac804c2d996052e9a5ec2df68bc5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208949"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes クラス
このクラスは、セキュリティ属性の構造体の thin ラッパーです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Csecurityattributes::set](#set)|属性を設定するには、このメソッドを呼び出して、`CSecurityAttributes`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `SECURITY_ATTRIBUTES`構造に含まれる、[セキュリティ記述子](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)のオブジェクトの作成に使用して、この構造体を指定することによって取得されたハンドルが継承可能かどうかを指定します。  
  
 Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes  
 コンストラクターです。  
  
```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSecurityDescriptor*  
 セキュリティ記述子への参照。  
  
 *bInheritsHandle*  
 新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。  
  
##  <a name="set"></a>  Csecurityattributes::set  
 属性を設定するには、このメソッドを呼び出して、`CSecurityAttributes`オブジェクト。  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 *rSecurityDescriptor*  
 セキュリティ記述子への参照。  
  
 *bInheritHandle*  
 新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、コンス トラクターで初期化するために使用されます、`CSecurityAttributes`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [セキュリティのサンプル](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [セキュリティ記述子](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
