---
title: 'データ ソース: プログラムにおける ODBC データ ソースの設定'
ms.date: 11/04/2016
f1_keywords:
- SQLConfigDataSource
helpviewer_keywords:
- ODBC data sources, configuring
- SQLConfigDataSource method example
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
ms.openlocfilehash: 38f0f383256a05c983fb7e7d7a498e16881c7b78
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545961"
---
# <a name="data-source-programmatically-configuring-an-odbc-data-source"></a>データ ソース: プログラムにおける ODBC データ ソースの設定

このトピックでは、ODBC (Open Database Connectivity) データ ソース名をプログラムで設定する方法について説明します。 この方法を使うと、柔軟なデータ アクセスが可能になり、ユーザーが ODBC データ ソース アドミニストレーターなどのプログラムを使って明示的にデータ ソースを指定する必要もありません。

通常、ユーザーは ODBC データ ソース アドミニストレーターを実行してデータ ソースを作成します。ただし、関連付けられたデータベース管理システム (DBMS: Database Management System) がこの操作をサポートすることが条件です。

ODBC データ ソース アドミニストレーターを使用して Microsoft Access ODBC データ ソースを作成する際には、既存の .mdb ファイルを使用するか、新しい .mdb ファイルを作成するかを選択できます。 MFC ODBC アプリケーションからプログラムを通じて .mdb ファイルを作成する方法はありません。 したがって、データを Microsoft Access データ ソース (.mdb ファイル) に格納する必要があるアプリケーションの場合は、空の .mdb ファイルを用意し、必要に応じて使用またはコピーできるようにします。

しかし、多くの DBMS では、プログラム上でデータ ソースを作成できます。 一部のデータ ソースは、データベースのフォルダー仕様を保持しています。 つまり、フォルダーがデータ ソースであり、データ ソース内の各テーブルは別個のファイルに格納されます。たとえば、dBASE の場合、各テーブルは .dbf ファイルです。 Microsoft Access や SQL Server などの他の ODBC データベースのドライバーでは、データソースを確立する前に特定の条件を満たす必要があります。 たとえば、SQL Server ODBC ドライバーを使用する場合は、SQL Server コンピューターを確立しておく必要があります。

##  <a name="sqlconfigdatasource-example"></a><a name="_core_sqlconfigdatasource_example"></a>SQLConfigDataSource の例

次の例では、`::SQLConfigDataSource` ODBC API 関数を使用して、新しい excel データソースという新しい Excel データソースを作成します。

```
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",
                   "DSN=New Excel Data Source\0"
                   "Description=New Excel Data Source\0"
                   "FileType=Excel\0"
                   "DataDirectory=C:\\EXCELDIR\0"
                   "MaxScanRows=20\0");
```

このデータ ソースは、実際はフォルダー (C:\EXCELDIR) です。このフォルダーは存在している必要があります。 Excel ドライバーは、フォルダーをそのデータ ソースとして使用し、ファイルを各テーブル (.xls ファイルごとに 1 テーブル) として使用するからです。

テーブルの作成の詳細については、「[データソース: プログラムによって ODBC データソースにテーブルを作成](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)する」を参照してください。

次の情報では、`::SQLConfigDataSource` ODBC API 関数に渡す必要があるパラメーターについて説明します。 `::SQLConfigDataSource`を使用するには、Odbcinst .h ヘッダーファイルをインクルードし、Odbcinst インポートライブラリを使用する必要があります。 また、実行時には、パスに Odbccp32.dll (16 ビットの場合は Odbcinst.dll) を指定する必要があります。

ODBC データ ソース名は、ODBC データ ソース アドミニストレーターなどのユーティリティを使用して作成できます。 しかし、アプリケーションから直接データ ソース名を作成し、ユーザーが別のユーティリティを実行しなくてもアクセスできるようにする方が望ましい場合もあります。

通常、ODBC データ ソース アドミニストレーターは、コントロール パネルにインストールされます。ODBC データ ソース アドミニストレーターは、Windows レジストリ (16 ビットの場合は Odbc.ini ファイル) にエントリを追加することによって、新しいデータ ソースを作成します。 ODBC ドライバー マネージャーは、このファイルを問い合わせてデータ ソースに関する必要な情報を取得します。 `::SQLConfigDataSource`の呼び出しを使用して指定する必要があるため、レジストリにどのような情報を配置する必要があるかを把握しておくことが重要です。

この情報は `::SQLConfigDataSource`を使用せずにレジストリに直接書き込むこともできますが、そのようなアプリケーションは、そのデータを保持するためにドライバーマネージャーが使用する現在の手法に依存しています。 新しいバージョンの ODBC ドライバー マネージャーでデータ ソースのレコードを保持する方法に変更があると、この手法を使うアプリケーションは動作しなくなります。 API 関数が提供されている場合はできるだけそれを使うようにしてください。 たとえば、関数が Odbc .ini ファイルまたはレジストリに正しく書き込みを行うため、`::SQLConfigDataSource` 関数を使用する場合、コードは16ビットから32ビットに移植できます。

##  <a name="sqlconfigdatasource-parameters"></a><a name="_core_sqlconfigdatasource_parameters"></a>SQLConfigDataSource パラメーター

次に、`::SQLConfigDataSource` 関数のパラメーターについて説明します。 多くの情報は、Visual C++バージョン1.5 以降で提供されている ODBC API*プログラマーリファレンス*から取得されています。

###  <a name="function-prototype"></a><a name="_core_function_prototype"></a>関数プロトタイプ

```
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);
```

### <a name="remarks"></a>コメント

####  <a name="parameters-and-usage"></a><a name="_core_parameters_and_usage"></a>パラメーターと使用法

*hwndParent*<br/>
新しいデータ ソースに関する追加情報をユーザーから得るために ODBC ドライバー マネージャーまたは特定の ODBC ドライバーが作成するダイアログ ボックスのオーナーとして指定するウィンドウ。 *Lpszattributes*パラメーターに十分な情報が指定されていない場合は、ダイアログボックスが表示されます。 *HwndParent*パラメーターは NULL にすることができます。

*lpszDriver*<br/>
ドライバーの名前。 ユーザーに示す名前であり、物理ドライバー名 (DLL) ではありません。

*lpszAttributes*<br/>
"キー名=値" 形式で指定する属性リスト。 各文字列は NULL ターミネータで区切ります。属性リストの最後には NULL ターミネータを 2 つ続けます。 これらの属性は、主として既定のドライバー固有のエントリであり、新しいデータ ソースのレジストリに入ります。 『ODBC API Reference』には説明されていないこの関数の重要なエントリとして、"DSN (data source name)" があります。DSN では、新しいデータ ソースの名前を指定します。 残りのエントリは、新しいデータ ソースのドライバー固有のエントリです。 エントリをすべて指定する必要はありません。ドライバーは、ダイアログ ボックスを表示してユーザーに新しい値を指定させることができるからです。 (これを発生させるには、 *hwndParent*を NULL に設定します)。ユーザーにプロンプトが表示されないように、既定値を明示的に指定することもできます。

#### <a name="to-determine-the-description-of-a-driver-for-the-lpszdriver-parameter-using-odbc-administrator"></a>ODBC データ ソース アドミニストレーターを使用して lpszDriver パラメーターのドライバー名を指定するには

1. ODBC データ ソース アドミニストレーターを実行します。

1. **[追加]** をクリックします。

これにより、インストールされているドライバーとその記述の一覧が表示されます。 この説明を*Lpszdriver*パラメーターとして使用します。 なお、その際には記述全体を使います。たとえば、"Excel Files (*.xls)" という記述の場合は、ファイル拡張子とかっこも含めます。

別の方法として、レジストリ (16 ビットの場合は Odbcinst.ini ファイル) でレジストリ キー "ODBC Drivers" (Odbcinst.ini の場合は [ODBC Drivers] セクション) の下のすべてのドライバー エントリと記述の一覧を調べることもできます。

*Lpszattributes*パラメーターのキー名と値を確認する方法の1つは、既に構成されているデータソース (Odbc 管理者によって構成されたもの) の Odbc .ini ファイルを調べることです。

#### <a name="to-find-keynames-and-values-for-the-lpszattributes-parameter"></a>lpszAttributes パラメーターのキー名と値を探すには

1. Windows レジストリ エディターを実行します (16 ビットの場合は Odbc.ini ファイルを開きます)。

1. 次のいずれかの方法を使用して ODBC データ ソース情報を検索します。

   - 32ビットの場合は、キー **HKEY_CURRENT_USER を見つけます。** 左側のウィンドウでデータソースを INI\ODBC します。

      右側のペインには、"pub: REG_SZ: *\<データソース名 >* " という形式のエントリが一覧表示されます。ここで、 *\<データソース名 >* は、使用するドライバーに必要な設定で既に構成されているデータソースです。 必要なデータソース (たとえば、SQL Server) を選択します。 文字列 "pub:" に続く項目は、 *Lpszattributes*パラメーターで使用する keyname と値を順に示しています。

   - 16ビットの場合は、[ *\<データソース名 >* ] でマークされた Odbc .ini ファイル内のセクションを見つけます。

      この行の後には、"キー名=値" という形式の行が続きます。 これらは、 *Lpszattributes*パラメーターで使用するエントリです。

使用する特定のドライバーに関するドキュメントを調べるには、ドライバーのオンライン ヘルプを参照してください。 ドライバーのオンライン ヘルプにアクセスするには、ODBC データ ソース アドミニストレーターを実行します。 これらのヘルプファイルは、通常、Windows NT、Windows 3.1、または Windows 95 の WINDOWS\SYSTEM ディレクトリに配置されます。

#### <a name="to-obtain-online-help-for-your-odbc-driver"></a>ODBC ドライバーのオンライン ヘルプを参照するには

1. ODBC データ ソース アドミニストレーターを実行します。

1. **[追加]** をクリックします。

1. ドライバー名を選択します。

1. **[OK]** をクリックすると、

ODBC 管理者が、その特定のドライバーの新しいデータソースを作成するための情報を表示する場合は、 **[ヘルプ]** をクリックします。 このドライバーのヘルプ ファイルが開き、通常は、ドライバーの使い方に関する重要な情報が表示されます。

## <a name="see-also"></a>参照

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)
