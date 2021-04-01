---
title: API に関する作業
description: API を使用し、制限を把握します。
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710466"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insights API の使用

Dynamics 365 Customer Insights は、Customer Insights のデータに基づいて、独自のアプリケーションを構築するための API を提供します。

> [!IMPORTANT]
> これらの API の詳細は、[Customer Insights API リファレンス](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) に一覧表示されます。 これらには、操作、パラメーター、および応答に関する追加情報が含まれています。

この記事では、Customer Insights API にアクセスし、Azure アプリの登録を作成して、利用可能なクライアント ライブラリの使用を開始する方法について説明します。

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insights API の試用を開始する

1. Customer Insights に [サインイン](https://home.ci.ai.dynamics.com) します。 まだサブスクリプションをお持ちでない場合は、[Customer Insights の試用版にサインアップ](https://aka.ms/tryci) します。

1. Customer Insights 環境で API を有効にするには、**管理** > **アクセス許可** に移動します。 これを行うには、管理者のアクセス許可が必要です。

1. **API** タブに移動し、**有効** ボタンを選択します。    
   API を有効にすると、API 要求で使用されるインスタンスに対してプライマリおよびセカンダリのサブスクリプション キーが作成されます。 キーを再生成するには、**管理** > **アクセス許可** > **API** で **プライマリの再生成** または **セカンダリの再生成** を選択します。

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insights API を有効にする":::

1. **API の詳細を確認** を選択して、[API を試してください](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances)。

1. API 操作を選択して、**テスト** を選択します。

1. サイド ペインで、**承認** ドロップダウン メニューの値を **暗黙** に設定します。 `Authorization` ヘッダーは、ベアラー トークンが追加された状態で取得されます。 サブスクリプション キーは自動的に入力されます。
  
1. 必要に応じて、必要なすべてのクエリ パラメーターを追加します。

1. サイド ペインの下までスクロールして、**送信** を選択します。

HTTP 応答がすぐに下に表示されます。


   :::image type="content" source="media/try-apis.gif" alt-text="API のテストを選択する方法を示すアニメーション gif。":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Azure portal で新しいアプリの登録を作成する

これらの手順は、委任されたアクセス許可を使用して、Azure アプリケーションで Customer Insights API の使用を開始するのに役立ちます。 最初に [「開始する」のセクション](#get-started-trying-the-customer-insights-apis) を完了していることを確認してください。

1. Customer Insights データにアクセスできるアカウントで [Azure portal](https://portal.azure.com) にサインインします。

1. 左側で、**アプリの登録** を選択します。

1. **新規登録** を選択して、アプリケーション名を入力し、アカウントの種類を選択します。
   必要に応じて、リダイレクト URL を追加します。 ローカル コンピュータでアプリケーションを開発するには、http://localhost で十分です。

1. 新しいアプリの登録で、**API アクセス許可** に移動します。

   :::image type="content" source="media/app-registration-1.gif" alt-text="アプリ登録で API アクセス許可を設定するためのアニメーション gif。":::

1. **アクセス許可の追加** を選択し、サイド ペインで **Customer Insights** を選択します。

1. **アクセス許可の種類** で **委任されたアクセス許可** を選択し、**user_impersonation** アクセス許可を選択します。

1. **アクセス許可の追加** を選択します。 ユーザーがログインせずに API にアクセスする必要がある場合は、[サーバー間アプリケーションのアクセス許可](#server-to-server-application-permissions) セクションを確認してください。

1. **... に管理者の同意を付与する** を選択して、アプリの登録を完了します。

Microsoft 認証ライブラリ (MSAL) でこのアプリの登録に使用されたアプリケーション/クライアント ID を使用して、API への要求とともに送信するベアラー トークンを取得できます。

:::image type="content" source="media/grant-admin-consent.gif" alt-text="管理者の同意を与えるアニメーション gif。":::

MSAL の詳細については、[Microsoft 認証ライブラリ (MSAL) の概要](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) を参照してください。

Azure でのアプリの登録の詳細については、[新しい Azure portal アプリの登録エクスペリエンス](/azure/active-directory/develop/app-registration-portal-training-guide) を参照してください。

クライアント ライブラリの API の使用については、[Customer Insights クライアント ライブラリ](#customer-insights-client-libraries) を参照してください。

### <a name="server-to-server-application-permissions"></a>サーバー間アプリケーションのアクセス許可

[アプリ登録セクション](#create-a-new-app-registration-in-the-azure-portal) では、ユーザーが認証のためにサインインする必要があるアプリを登録する方法の概要を説明します。 ユーザーの操作を必要とせず、サーバー上で実行できるアプリ登録の作成方法を説明します。

1. Azure portal のアプリの登録で、**API アクセス許可** に移動します。

1. **アクセス許可の追加** を選択し、サイド ペインで **Customer Insights** を選択します。

1. **アクセス許可の種類** で **アプリケーションのアクセス許可** を選択し、**CustomerInsights.Api.All** アクセス許可を選択します。

1. **アクセス許可の追加** を選択します。

1. このアプリケーションのアクセス許可に管理者の同意を付与するには、サービス プリンシパルを追加する必要があります。

   1. Azure Active Directory (AD) PowerShell モジュールをインストールします: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. AD アカウントに接続します: `Connect-AzureAD -TenantId <your tenant id>`。 テナント ID は **概要** > **Azure Active Directory** で確認できます。
   1. 次のコマンドを実行して、Azure AD サービス プリンシパルを追加します: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` AppId パラメーターは、Customer Insights API アプリに関連しています。

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="サービス プリンシパル サンプル":::

1. アプリの登録の **API アクセス許可** に戻ります。

1. **... に管理者の同意を付与する** を選択して、アプリの登録を完了します。

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="管理者の同意を与えるアニメーション gif。":::

1. 結論から言うと、アプリ登録の名前を Customer Insights でユーザーとして追加する必要があります。    
   Customer Insights を開き、**管理** > **アクセス許可** に移動し、**ユーザーの追加** を選択します。

1. アプリ登録の名前を検索し、検索結果から選択して、**保存** を選択します。

## <a name="customer-insights-client-libraries"></a>Customer Insights クライアント ライブラリ

このセクションは、Customer Insights API で使用可能なクライアント ライブラリを使い始めるときに役立ちます。 すべてのライブラリ ソース コードとサンプル アプリケーションについては、[Customer Insights GitHub ページ](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries) を参照してください。 

### <a name="c-nuget"></a>C# NuGet

NuGet.org から C# クライアント ライブラリを使い始める方法を説明します。NuGet パッケージの詳細については、[Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/) を参照してください。 現在、このパッケージは netstandard2.0 と netcoreapp2.0 フレームワークを対象としています。

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# クライアント ライブラリを C# プロジェクトに追加する

1. Visual Studio で、プロジェクトのために **NuGet パッケージ マネージャー** を開きます。

1. **Microsoft.Dynamics.CustomerInsights.Api** を検索します。

1. **インストール** を選択し、プロジェクトにパッケージを追加します。
   または、次のコマンドを **NuGet パッケージ マネージャー コンソール** で実行します: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGet パッケージを Visual Studio プロジェクトに追加する":::

#### <a name="use-the-c-client-library"></a>C# クライアント ライブラリを使用する

1. [Microsoft 認証ライブラリ (MSAL)](/azure/active-directory/develop/msal-overview) を使用し、既存の [Azure アプリの登録](#create-a-new-app-registration-in-the-azure-portal) を使用して `AccessToken` を取得します。

1. トークンの認証と取得に成功したら、新しい `HttpClient` を作成するか、既存のものを使用して、追加の **DefaultRequestHeaders "Authorization"** を **ベアラー <access token>** に設定し、**Ocp-Apim-Subscription-Key** を [Customer Insights 環境の **サブスクリプション キー**](#get-started-trying-the-customer-insights-apis) に設定します。    
   必要に応じて **Authorization** ヘッダーをリセットします。 たとえば、トークンの有効期限が切れたときです。

1. この `HttpClient` を `CustomerInsights` クライアントの構築に渡します。

   :::image type="content" source="media/httpclient-sample.png" alt-text="httpclient のサンプル":::

1. クライアントで、例えば `GetAllInstancesAsync` などの「拡張メソッド」を呼び出します。 基になる `Microsoft.Rest.HttpOperationResponse` へのアクセスが推奨される場合は、たとえば `GetAllInstancesWithHttpMessagesAsync` などの「HTTP メッセージ メソッド」を使用します。

1. メソッドは複数の型 (たとえば、`IList<InstanceInfo>` や `ApiErrorResult`) を返すことができるため、応答は `object` 型である可能性があります。 戻り値の型を確認するためには、その操作の [API 詳細ページ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) で指定した応答型にオブジェクトを安全にキャストできます。    
   要求に関する詳細情報が必要な場合は、**HTTP メッセージ メソッド** を使用して、未加工の応答オブジェクトにアクセスします。

### <a name="nodejs-package"></a>NodeJS パッケージ

NPM から入手できる NodeJS クライアント ライブラリを使用します: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python パッケージ

PyPi から入手できる Python クライアント ライブラリを使用します: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
