---
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
ms.openlocfilehash: e3b76be2a1f1edfcdc1139a3dd396835923c2b4a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210692"
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
`IConvertTypeImpl`から派生したクラス。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[CanConvert](#canconvert)|コマンドまたは行セットでの型変換の可用性に関する情報を提供します。|

## <a name="remarks"></a>解説

コマンド、行セット、およびインデックス行セットでは、このインターフェイスは必須です。 `IConvertTypeImpl` は、OLE DB によって提供される変換オブジェクトにを委任することによって、インターフェイスを実装します。

## <a name="iconverttypeimplcanconvert"></a><a name="canconvert"></a>IConvertTypeImpl:: CanConvert

コマンドまたは行セットでの型変換の可用性に関する情報を提供します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CanConvert)(DBTYPE wFromType,
   DBTYPE wToType,
   DBCONVERTFLAGS dwConvertFlags);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [Iconverttype:: canconvert](/previous-versions/windows/desktop/ms711224(v=vs.85)) 」を参照してください。

### <a name="remarks"></a>解説

`MSADC.DLL`で OLE DB データ変換を使用します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
