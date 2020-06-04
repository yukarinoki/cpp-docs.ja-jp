---
title: テンプレートインスタンス化クラス
description: C++ ビルド インサイト SDK テンプレートインスタンス化クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ba8fd10efc6a536c9160f10b19e19e17bfaaad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324218"
---
# <a name="templateinstantiation-class"></a>テンプレートインスタンス化クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`TemplateInstantiation`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation)イベントに一致させるために使用します。

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

クラスには、[その Activity](activity.md)基本クラスから継承された`TemplateInstantiation`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[テンプレートのインスタンス化](#template-instantiation)

### <a name="functions"></a>関数

[親切](#kind)
[なプライマリテンプレートシンボルキー](#primary-template-symbol-key)
[特化シンボルキー](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a>種類

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>戻り値

実行されたテンプレートのインスタンス化の種類を記述するコード。

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a>プライマリテンプレートシンボルキー

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>戻り値

特殊化されたテンプレート型の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a>特殊化シンボルキー

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>戻り値

特殊化の型の数値識別子。 この識別子は、コンパイラのフロントエンド パス内で一意です。

## <a name="templateinstantiation"></a><a name="template-instantiation"></a>テンプレートのインスタンス化

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation)イベント。

::: moniker-end
