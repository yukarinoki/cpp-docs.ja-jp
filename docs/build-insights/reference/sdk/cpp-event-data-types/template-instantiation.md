---
title: TemplateInstantiation クラス
description: C++ Build Insights SDK の TemplateInstantiation クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7ff03aaa431f5c5e217f605698a255686411b479
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920438"
---
# <a name="templateinstantiation-class"></a>TemplateInstantiation クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiation` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class TemplateInstantiation : public Activity
{
public:
    enum class Kind
    {
        CLASS       = TEMPLATE_INSTANTIATION_KIND_CODE_CLASS,
        FUNCTION    = TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION,
        VARIABLE    = TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE,
        CONCEPT     = TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT
    };

    TemplateInstantiation(const RawEvent& event);

    const unsigned long long& SpecializationSymbolKey() const;
    const unsigned long long& PrimaryTemplateSymbolKey() const;

    Kind Kind() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`TemplateInstantiation` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[TemplateInstantiation](#template-instantiation)

### <a name="functions"></a>機能

[Kind](#kind)
[PrimaryTemplateSymbolKey](#primary-template-symbol-key)
[SpecializationSymbolKey](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a> Kind

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>戻り値

実行されたテンプレートのインスタンス化の種類を表すコード。

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a> PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>戻り値

特殊化されたテンプレートの種類の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a> SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>戻り値

特殊化の種類の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="templateinstantiation"></a><a name="template-instantiation"></a> TemplateInstantiation

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) イベント。

::: moniker-end
