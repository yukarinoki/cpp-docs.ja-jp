---
title: クラスをインスタンス化する
description: C++ ビルド インサイト SDK テンプレートインスタンス化グループ クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 18dd48219c7c68ce152c381eb505fe37b19ec8dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324261"
---
# <a name="templateinstantiationgroup-class"></a>クラスをインスタンス化する

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`TemplateInstantiationGroup`は、[関数と一致イベント スタック](../functions/match-event-stack.md)と一致イベント[スタックInメンバー関数](../functions/match-event-stack-in-member-function.md)で使用されます。 この値は[、TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation)イベントのグループと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>メンバー

クラスには、継承されたメンバーが[EventGroup\<Template\>インスタンス化](event-group.md)基本クラス`TemplateInstantiationGroup`から継承されたメンバーと共に、次のメンバーが含まれています。

### <a name="constructors"></a>コンストラクター

[テンプレートインスタンス化グループ](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a>テンプレートインスタンス化グループ

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>パラメーター

*グループ*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation)イベントのグループ。

::: moniker-end
