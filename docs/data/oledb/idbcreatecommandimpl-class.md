---
title: IDBCreateCommandImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- IDBCreateCommandImpl::CreateCommand
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
ms.openlocfilehash: 27ca1fd20e8f358d936789da695611d96a6e7aa1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545823"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl クラス

[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class CommandClass >
class ATL_NO_VTABLE IDBCreateCommandImpl
   : public IDBCreateCommand
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`IDBCreateCommandImpl`から派生したセッションオブジェクト。

*CommandClass*<br/>
コマンドクラス。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[CreateCommand](#createcommand)|新しいコマンドを作成します。|

## <a name="remarks"></a>コメント

新しいコマンドを取得するための、セッションオブジェクトのオプションのインターフェイス。

## <a name="idbcreatecommandimplcreatecommand"></a><a name="createcommand"></a>IDBCreateCommandImpl:: CreateCommand

新しいコマンドを作成し、要求されたインターフェイスを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppvCommand);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IDBCreateCommand:: createcommand](/previous-versions/windows/desktop/ms709772(v=vs.85)) 」を参照してください。

一部のパラメーターは、`IDBCreateCommand::CreateCommand`で説明されているさまざまな名前の*プログラマの参照パラメーター OLE DB*に対応しています。

|テンプレートパラメーターの OLE DB|*OLE DB プログラマーの参照*パラメーター|
|--------------------------------|------------------------------------------------|
|*ppvCommand*|*ppCommand*|

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)