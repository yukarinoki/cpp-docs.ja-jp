---
title: ICommandTextImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: 7d31933b162a74db31bdd3c65dc68e396a3896c4
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501723"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl クラス

[ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したコマンドクラス `ICommandTextImpl` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** altdb .h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[GetCommandText](#getcommandtext)|[Setcommandtext](#setcommandtext)の最後の呼び出しで設定されたテキストコマンドを返します。|
|[SetCommandText](#setcommandtext)|既存のコマンドテキストを置き換えて、コマンドテキストを設定します。|

### <a name="data-members"></a>データ メンバー

| 名前 | 説明 |
|-|-|
|[m_strCommandText](#strcommandtext)|コマンドテキストを格納します。|

## <a name="remarks"></a>注釈

コマンドの必須のインターフェイスです。

## <a name="icommandtextimplgetcommandtext"></a><a name="getcommandtext"></a> ICommandTextImpl:: GetCommandText

[Setcommandtext](#setcommandtext)の最後の呼び出しで設定されたテキストコマンドを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandText:: getcommandtext](/previous-versions/windows/desktop/ms709825(v=vs.85)) 」を参照してください。 既定では、 *Pguiddialect* パラメーターは無視されます。

## <a name="icommandtextimplsetcommandtext"></a><a name="setcommandtext"></a> ICommandTextImpl:: SetCommandText

既存のコマンドテキストを置き換えて、コマンドテキストを設定します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [ICommandText:: setcommandtext](/previous-versions/windows/desktop/ms709757(v=vs.85)) 」を参照してください。

## <a name="icommandtextimplm_strcommandtext"></a><a name="strcommandtext"></a> ICommandTextImpl:: m_strCommandText

コマンドテキスト文字列を格納します。

### <a name="syntax"></a>構文

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
