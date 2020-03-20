---
title: 混合モードから純粋な中間言語へのプロジェクトの変換
ms.date: 08/19/2019
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
ms.openlocfilehash: 05ece23e6d79fc399085099deebcde0aa4a92c64
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2019
ms.locfileid: "79544736"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>混合モードから純粋な中間言語へのプロジェクトの変換

すべてのC++ Visual CLR プロジェクトは、既定で C ランタイムライブラリにリンクされます。 そのため、これらのプロジェクトは、共通言語ランタイム (マネージコード) を対象とするコードとネイティブコードを組み合わせるため、混合モードアプリケーションとして分類されます。 コンパイルされると、中間言語 (IL) にコンパイルされます。これは、Microsoft 中間言語 (MSIL) とも呼ばれます。

> [!IMPORTANT]
> Visual Studio 2015 では非推奨とされており、Visual Studio 2017 は CLR アプリケーションの **/clr: pure**または **/clr: safe**コードの作成をサポートしなくなりました。 純粋または安全なアセンブリが必要な場合は、アプリケーションをにC#変換することをお勧めします。

**/Clr: pure**または **/clr: safe**をサポートC++する以前のバージョンの Microsoft コンパイラツールセットを使用している場合は、次の手順を使用してコードを純粋 MSIL に変換できます。

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>混合モードアプリケーションを純粋中間言語に変換するには

1. [C ランタイムライブラリ](../c-runtime-library/crt-library-features.md)へのリンクを削除する (CRT):

   1. アプリケーションのエントリポイントを定義する .cpp ファイルで、エントリポイントを `Main()`に変更します。 `Main()` を使用すると、プロジェクトが CRT にリンクしないことを示します。

   2. ソリューションエクスプローラーで、プロジェクトを右クリックし、ショートカットメニューの **[プロパティ]** を選択して、アプリケーションのプロパティページを開きます。

   3. **リンカー**の **[** プロジェクトの詳細プロパティ] ページで、**エントリポイント**を選択し、このフィールドに「 **Main** 」と入力します。

   4. コンソールアプリケーションの場合は、**リンカー**の**システム**プロジェクトプロパティページで **[サブシステム]** フィールドを選択し、これを **[コンソール (/SUBSYSTEM: コンソール)]** に変更します。

      > [!NOTE]
      > 既定では、**サブシステム**フィールドが**Windows (/SUBSYSTEM: windows)** に設定されているため Windows フォームアプリケーションに対してこのプロパティを設定する必要はありません。

   5. *Stdafx.h*で、すべての `#include` ステートメントをコメントアウトします。 たとえば、コンソールアプリケーションでは次のようになります。

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       または

       たとえば、Windows フォームアプリケーションの場合は、次のようになります。

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Windows フォームアプリケーションの場合は、Form1 で、Windows .h を参照する `#include` ステートメントをコメントアウトします。 例 :

      ```cpp
      // #include <windows.h>
      ```

2. 次のコードを stdafx.h に追加し*ます*。

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. すべてのアンマネージ型を削除します。

   必要に応じて、アンマネージ型を[System](/dotnet/api/system)名前空間の構造体への参照に置き換えます。 一般的なマネージ型を次の表に示します。

   |構造体|説明|
   |---------------|-----------------|
   |[Boolean](/dotnet/api/system.boolean)|ブール値を表します。|
   |[Byte](/dotnet/api/system.byte)|8 ビット符号なし整数を表します。|
   |[Char](/dotnet/api/system.char)|Unicode 文字を表します。|
   |[DateTime](/dotnet/api/system.datetime)|特定の時点を表します。通常、日時形式で表されます。|
   |[Decimal](/dotnet/api/system.decimal)|10 進数を表します。|
   |[Double](/dotnet/api/system.double)|倍精度浮動小数点数を表します。|
   |[Guid](/dotnet/api/system.guid)|グローバル一意識別子 (GUID) を表します。|
   |[Int16](/dotnet/api/system.int16)|16 ビット符号付き整数を表します。|
   |[Int32](/dotnet/api/system.int32)|32 ビット符号付き整数を表します。|
   |[Int64](/dotnet/api/system.int64)|64 ビット符号付き整数を表します。|
   |[IntPtr](/dotnet/api/system.intptr)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|
   |[SByte](/dotnet/api/system.byte)|8 ビット符号付き整数を表します。|
   |[Single](/dotnet/api/system.single)|単精度浮動小数点数を表します。|
   |[TimeSpan](/dotnet/api/system.timespan)|時間間隔を表します。|
   |[UInt16](/dotnet/api/system.uint16)|16 ビット符号なし整数を表します。|
   |[UInt32](/dotnet/api/system.uint32)|32 ビット符号なし整数を表します。|
   |[UInt64](/dotnet/api/system.uint64)|64 ビット符号なし整数を表します。|
   |[UIntPtr](/dotnet/api/system.uintptr)|ポインターまたはハンドルを表すときに使用されるプラットフォーム固有の型。|
   |[無効化](/dotnet/api/system.void)|値を返さないメソッドを示します。つまり、メソッドの戻り値の型は void です。|