---
title: CLR 統合 (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: df0c5e9cfaf9a4148c8d16b68ee04b4e9ce82e6a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749024"
---
# <a name="clr-integration-ccx"></a>CLR 統合 (C++/CX)

いくつかの Windows ランタイム型では、特別な処理を受け取る c++/cli CX および共通言語ランタイム (CLR) に基づく言語です。 この記事では、1 つの言語のいくつかの型から別の言語へのマップの仕組みについて説明します。 たとえば、CLR は Windows.Foundation.IVector を System.Collections.IList へ、Windows.Foundation.IMap を System.Collections.IDictionary へ、というようにマップします。 同様に、C + + CX は platform::delegate や platform::string などの型を特別にマップします。

## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows ランタイムをマッピングする C + + CX

ときに C +/cli CX は Windows メタデータ (.winmd) ファイルを読み取り、コンパイラは一般的な Windows ランタイム名前空間と型を自動的にマップすると c++/cli/CX 名前空間と型。 たとえば、数値の Windows ランタイム型`UInt32`に自動的にマップされます`default::uint32`します。

C +/cli CX に他のいくつかの Windows ランタイム型をマップする、**プラットフォーム**名前空間。 たとえば、 **windows::foundation**読み取り専用の Unicode テキスト文字列を表す、HSTRING ハンドルが C + マップ/cli CX`Platform::String`クラス。 C + にマップされている Windows のランタイム操作には、エラーの hresult 値が返される、ときに/cli CX`Platform::Exception`します。

C++/cli CX では、特定の種類を型の機能を強化するために Windows ランタイム名前空間にもマップされます。 このような種類 C + + CX ヘルパー コンス トラクターとは C++ に固有であり、型の標準 .winmd ファイルでは使用できませんメソッドを提供します。

新しいコンストラクターとヘルパー メソッドをサポートしている値構造体を次の一覧に示します。 構造体の初期化リストを使用するコードを既に作成済みの場合、新たに追加されたコンストラクターを使用するように変更してください。

**Windows::Foundation**

- ポイント

- Rect

- サイズ

**Windows::UI**

- 色

**Windows::UI::Xaml**

- CornerRadius

- 存続期間

- GridLength

- 太さ

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- [マトリックス]

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>マッピング CLR の c++/cli CX

Visual C または c# のコンパイラでは、.winmd ファイルを読み取り、それらのメタデータ ファイルで特定の種類を適切な C + に自動的にマップ/cli/CX または CLR 型。 CLR は、IVector\<T > インターフェイスが IList にマップされている\<T >。 C++/cli CX、IVector\<T > インターフェイスは別の型にマップされていません。

IReference\<T >、Windows ランタイムで null 値にマップされます\<T > で .NET。

## <a name="see-also"></a>関連項目

[その他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)
