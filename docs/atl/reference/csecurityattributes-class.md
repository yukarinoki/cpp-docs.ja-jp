---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: 113bcebb7461415590156206ee7aa4c91e0e93d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330984"
---
# <a name="csecurityattributes-class"></a>クラス

このクラスは、セキュリティ属性構造のシン ラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の属性::Cセキュリティ属性](#csecurityattributes)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[セキュリティ属性::セット](#set)|`CSecurityAttributes`オブジェクトの属性を設定します。|

## <a name="remarks"></a>解説

構造体`SECURITY_ATTRIBUTES`には、オブジェクトの作成に使用される[セキュリティ記述子](/windows/win32/api/winnt/ns-winnt-security_descriptor)が含まれ、この構造体を指定して取得したハンドルを継承可能にするかどうかを指定します。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a>次の属性::Cセキュリティ属性

コンストラクターです。

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*記述子*<br/>
セキュリティ記述子への参照。

*ハンドルを継承します。*<br/>
新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。

## <a name="csecurityattributesset"></a><a name="set"></a>セキュリティ属性::セット

`CSecurityAttributes`オブジェクトの属性を設定します。

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>パラメーター

*記述子*<br/>
セキュリティ記述子への参照。

*ハンドルを継承*<br/>
新しいプロセスの作成時に、返されたハンドルを継承するかどうかを指定します。 このメンバーが true の場合、新しいプロセスは、返されたハンドルを継承します。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトを初期化するためにコンストラクターによって`CSecurityAttributes`使用されます。

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[セキュリティ記述子](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
