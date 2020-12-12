---
description: '詳細情報: IConvertTypeImpl クラス'
title: IConvertTypeImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
- IConvertTypeImpl.CanConvert
- CanConvert
- IConvertTypeImpl::CanConvert
helpviewer_keywords:
- IConvertTypeImpl class
- CanConvert method
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
ms.openlocfilehash: 5ac0e70432dbb81bd3f8aa30fd2adb9cb9e3fc30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317566"
---
# <a name="iconverttypeimpl-class"></a>IConvertTypeImpl クラス

[Iconverttype](/previous-versions/windows/desktop/ms715926(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE IConvertTypeImpl
   : public IConvertType, public CConvertHelper
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IConvertTypeImpl` 。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[CanConvert](#canconvert)|コマンドまたは行セットでの型変換の可用性に関する情報を提供します。|

## <a name="remarks"></a>解説

コマンド、行セット、およびインデックス行セットでは、このインターフェイスは必須です。 `IConvertTypeImpl` OLE DB によって提供される変換オブジェクトにを委任することによって、インターフェイスを実装します。

## <a name="iconverttypeimplcanconvert"></a><a name="canconvert"></a> IConvertTypeImpl:: CanConvert

コマンドまたは行セットでの型変換の可用性に関する情報を提供します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [Iconverttype:: canconvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

では、OLE DB データ変換を使用 `MSADC.DLL` します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
