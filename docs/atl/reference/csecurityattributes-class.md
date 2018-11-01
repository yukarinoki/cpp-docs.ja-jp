---
title: CSecurityAttributes クラス
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: 0b39109bd97e2bb83b7a51fdd6e626b63c4c8798
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604986"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

コンストラクターです。

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSecurityDescriptor*<br/>
セキュリティ記述子への参照。

*bInheritsHandle*<br/>
新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。

##  <a name="set"></a>  Csecurityattributes::set

属性を設定するには、このメソッドを呼び出して、`CSecurityAttributes`オブジェクト。

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSecurityDescriptor*<br/>
セキュリティ記述子への参照。

*bInheritHandle*<br/>
新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。

### <a name="remarks"></a>Remarks

このメソッドは、コンス トラクターで初期化するために使用されます、`CSecurityAttributes`オブジェクト。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[セキュリティ記述子](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
