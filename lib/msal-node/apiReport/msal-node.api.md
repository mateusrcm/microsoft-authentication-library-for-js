## API Report File for "@azure/msal-node"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

// @public
export type AccountInfo = {
    homeAccountId: string;
    environment: string;
    tenantId: string;
    username: string;
    localAccountId: string;
    name?: string;
    idTokenClaims?: object;
};

// @public
export type AuthenticationResult = {
    authority: string;
    uniqueId: string;
    tenantId: string;
    scopes: Array<string>;
    account: AccountInfo | null;
    idToken: string;
    idTokenClaims: object;
    accessToken: string;
    fromCache: boolean;
    expiresOn: Date | null;
    tokenType: string;
    extExpiresOn?: Date;
    state?: string;
    familyId?: string;
    cloudGraphHostName?: string;
    msGraphHost?: string;
};

// @public
export class AuthError extends Error {
    constructor(errorCode?: string, errorMessage?: string, suberror?: string);
    static createUnexpectedError(errDesc: string): AuthError;
    // (undocumented)
    errorCode: string;
    // (undocumented)
    errorMessage: string;
    // (undocumented)
    subError: string;
}

// @public
export const AuthErrorMessage: {
    unexpectedError: {
        code: string;
        desc: string;
    };
};

// Warning: (ae-forgotten-export) The symbol "AuthorizationCodeRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type AuthorizationCodeRequest = Partial<Omit<AuthorizationCodeRequest_2, "scopes" | "redirectUri" | "code" | "authenticationScheme" | "resourceRequestMethod" | "resourceRequestUri">> & {
    scopes: Array<string>;
    redirectUri: string;
    code: string;
};

// Warning: (ae-forgotten-export) The symbol "AuthorizationUrlRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type AuthorizationUrlRequest = Partial<Omit<AuthorizationUrlRequest_2, "scopes" | "redirectUri" | "resourceRequestMethod" | "resourceRequestUri" | "authenticationScheme">> & {
    scopes: Array<string>;
    redirectUri: string;
};

// @public
export function buildAppConfiguration({ auth, cache, system, }: Configuration): Configuration;

// Warning: (ae-forgotten-export) The symbol "ValidCacheType" needs to be exported by the entry point index.d.ts
//
// @public (undocumented)
export type CacheKVStore = Record<string, ValidCacheType>;

// @public (undocumented)
export abstract class ClientApplication {
    protected constructor(configuration: Configuration);
    acquireTokenByCode(request: AuthorizationCodeRequest): Promise<AuthenticationResult | null>;
    acquireTokenByRefreshToken(request: RefreshTokenRequest): Promise<AuthenticationResult | null>;
    acquireTokenSilent(request: SilentFlowRequest): Promise<AuthenticationResult | null>;
    // Warning: (ae-forgotten-export) The symbol "ServerTelemetryManager" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "ClientConfiguration" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    protected buildOauthClientConfiguration(authority: string, serverTelemetryManager?: ServerTelemetryManager): Promise<ClientConfiguration>;
    // Warning: (ae-forgotten-export) The symbol "ClientAssertion" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    protected clientAssertion: ClientAssertion;
    // (undocumented)
    protected clientSecret: string;
    // (undocumented)
    protected config: Configuration;
    getAuthCodeUrl(request: AuthorizationUrlRequest): Promise<string>;
    getLogger(): Logger;
    getTokenCache(): TokenCache;
    // Warning: (ae-forgotten-export) The symbol "BaseAuthRequest" needs to be exported by the entry point index.d.ts
    protected initializeBaseRequest(authRequest: Partial<BaseAuthRequest>): BaseAuthRequest;
    // (undocumented)
    protected initializeServerTelemetryManager(apiId: number, correlationId: string, forceRefresh?: boolean): ServerTelemetryManager;
    // (undocumented)
    protected logger: Logger;
    setLogger(logger: Logger): void;
    // (undocumented)
    protected storage: Storage_2;
    }

// @public
export class ClientAuthError extends AuthError {
    constructor(errorCode: string, errorMessage?: string);
    static createAppendEmptyScopeToSetError(givenScope: string): ClientAuthError;
    static createAppendScopeSetError(appendError: string): ClientAuthError;
    static createCachePluginError(): ClientAuthError;
    static createClientInfoDecodingError(caughtError: string): ClientAuthError;
    static createClientInfoEmptyError(): ClientAuthError;
    static createDeviceCodeCancelledError(): ClientAuthError;
    static createDeviceCodeExpiredError(): ClientAuthError;
    // Warning: (ae-forgotten-export) The symbol "ScopeSet" needs to be exported by the entry point index.d.ts
    static createEmptyInputScopeSetError(givenScopeSet: ScopeSet): ClientAuthError;
    static createEndpointDiscoveryIncompleteError(errDetail: string): ClientAuthError;
    static createHashNotDeserializedError(hashParamObj: string): ClientAuthError;
    static createInvalidAssertionError(): ClientAuthError;
    static createInvalidCacheEnvironmentError(): ClientAuthError;
    static createInvalidCacheTypeError(): ClientAuthError;
    static createInvalidCredentialError(): ClientAuthError;
    static createInvalidStateError(invalidState: string, errorString?: string): ClientAuthError;
    static createMultipleMatchingAccountsInCacheError(): ClientAuthError;
    static createMultipleMatchingAppMetadataInCacheError(): ClientAuthError;
    static createMultipleMatchingTokensInCacheError(): ClientAuthError;
    static createNoAccountFoundError(): ClientAuthError;
    static createNoAccountInSilentRequestError(): ClientAuthError;
    static createNoAuthCodeInServerResponseError(): ClientAuthError;
    static createNoCryptoObjectError(operationName: string): ClientAuthError;
    static createNonceMismatchError(): ClientAuthError;
    static createNonceNotFoundError(missingNonce: string): ClientAuthError;
    static createNoTokensFoundError(): ClientAuthError;
    static createNullOrUndefinedCacheRecord(): ClientAuthError;
    static createRefreshRequiredError(): ClientAuthError;
    static createRemoveEmptyScopeFromSetError(givenScope: string): ClientAuthError;
    static createStateMismatchError(): ClientAuthError;
    static createStateNotFoundError(missingState: string): ClientAuthError;
    // (undocumented)
    static createTokenClaimsRequiredError(): ClientAuthError;
    static createTokenNullOrEmptyError(invalidRawTokenString: string): ClientAuthError;
    static createTokenParsingError(caughtExtractionError: string): ClientAuthError;
    static createTokenRequestCannotBeMadeError(): ClientAuthError;
    static createUnableToGetOpenidConfigError(errDetail: string): ClientAuthError;
    static createUnexpectedAccountTypeError(): ClientAuthError;
    static createUnexpectedCredentialTypeError(): ClientAuthError;
    static createUserTimeoutReachedError(): ClientAuthError;
}

// @public
export const ClientAuthErrorMessage: {
    clientInfoDecodingError: {
        code: string;
        desc: string;
    };
    clientInfoEmptyError: {
        code: string;
        desc: string;
    };
    tokenParsingError: {
        code: string;
        desc: string;
    };
    nullOrEmptyToken: {
        code: string;
        desc: string;
    };
    endpointResolutionError: {
        code: string;
        desc: string;
    };
    unableToGetOpenidConfigError: {
        code: string;
        desc: string;
    };
    hashNotDeserialized: {
        code: string;
        desc: string;
    };
    blankGuidGenerated: {
        code: string;
        desc: string;
    };
    invalidStateError: {
        code: string;
        desc: string;
    };
    stateMismatchError: {
        code: string;
        desc: string;
    };
    stateNotFoundError: {
        code: string;
        desc: string;
    };
    nonceMismatchError: {
        code: string;
        desc: string;
    };
    nonceNotFoundError: {
        code: string;
        desc: string;
    };
    noTokensFoundError: {
        code: string;
        desc: string;
    };
    multipleMatchingTokens: {
        code: string;
        desc: string;
    };
    multipleMatchingAccounts: {
        code: string;
        desc: string;
    };
    multipleMatchingAppMetadata: {
        code: string;
        desc: string;
    };
    tokenRequestCannotBeMade: {
        code: string;
        desc: string;
    };
    appendEmptyScopeError: {
        code: string;
        desc: string;
    };
    removeEmptyScopeError: {
        code: string;
        desc: string;
    };
    appendScopeSetError: {
        code: string;
        desc: string;
    };
    emptyInputScopeSetError: {
        code: string;
        desc: string;
    };
    DeviceCodePollingCancelled: {
        code: string;
        desc: string;
    };
    DeviceCodeExpired: {
        code: string;
        desc: string;
    };
    NoAccountInSilentRequest: {
        code: string;
        desc: string;
    };
    invalidCacheRecord: {
        code: string;
        desc: string;
    };
    invalidCacheEnvironment: {
        code: string;
        desc: string;
    };
    noAccountFound: {
        code: string;
        desc: string;
    };
    CachePluginError: {
        code: string;
        desc: string;
    };
    noCryptoObj: {
        code: string;
        desc: string;
    };
    invalidCacheType: {
        code: string;
        desc: string;
    };
    unexpectedAccountType: {
        code: string;
        desc: string;
    };
    unexpectedCredentialType: {
        code: string;
        desc: string;
    };
    invalidAssertion: {
        code: string;
        desc: string;
    };
    invalidClientCredential: {
        code: string;
        desc: string;
    };
    tokenRefreshRequired: {
        code: string;
        desc: string;
    };
    userTimeoutReached: {
        code: string;
        desc: string;
    };
    tokenClaimsRequired: {
        code: string;
        desc: string;
    };
    noAuthorizationCodeFromServer: {
        code: string;
        desc: string;
    };
};

// @public
export class ClientConfigurationError extends ClientAuthError {
    constructor(errorCode: string, errorMessage?: string);
    static createClaimsRequestParsingError(claimsRequestParseError: string): ClientConfigurationError;
    static createClientIdSingleScopeError(inputScopes: Array<string>): ClientConfigurationError;
    static createEmptyLogoutRequestError(): ClientConfigurationError;
    static createEmptyScopesArrayError(inputScopes: Array<string>): ClientConfigurationError;
    static createEmptyTokenRequestError(): ClientConfigurationError;
    static createInsecureAuthorityUriError(urlString: string): ClientConfigurationError;
    static createInvalidAuthorityMetadataError(): ClientConfigurationError;
    static createInvalidClaimsRequestError(): ClientConfigurationError;
    static createInvalidCloudDiscoveryMetadataError(): ClientConfigurationError;
    static createInvalidCodeChallengeMethodError(): ClientConfigurationError;
    static createInvalidCodeChallengeParamsError(): ClientConfigurationError;
    static createInvalidPromptError(promptValue: string): ClientConfigurationError;
    static createPostLogoutRedirectUriEmptyError(): ClientConfigurationError;
    static createRedirectUriEmptyError(): ClientConfigurationError;
    static createResourceRequestParametersRequiredError(): ClientConfigurationError;
    static createScopesNonArrayError(inputScopes: Array<string>): ClientConfigurationError;
    static createUntrustedAuthorityError(): ClientConfigurationError;
    static createUrlEmptyError(): ClientConfigurationError;
    static createUrlParseError(urlParseError: string): ClientConfigurationError;
}

// @public
export const ClientConfigurationErrorMessage: {
    redirectUriNotSet: {
        code: string;
        desc: string;
    };
    postLogoutUriNotSet: {
        code: string;
        desc: string;
    };
    claimsRequestParsingError: {
        code: string;
        desc: string;
    };
    authorityUriInsecure: {
        code: string;
        desc: string;
    };
    urlParseError: {
        code: string;
        desc: string;
    };
    urlEmptyError: {
        code: string;
        desc: string;
    };
    emptyScopesError: {
        code: string;
        desc: string;
    };
    nonArrayScopesError: {
        code: string;
        desc: string;
    };
    clientIdSingleScopeError: {
        code: string;
        desc: string;
    };
    invalidPrompt: {
        code: string;
        desc: string;
    };
    invalidClaimsRequest: {
        code: string;
        desc: string;
    };
    tokenRequestEmptyError: {
        code: string;
        desc: string;
    };
    logoutRequestEmptyError: {
        code: string;
        desc: string;
    };
    invalidCodeChallengeMethod: {
        code: string;
        desc: string;
    };
    invalidCodeChallengeParams: {
        code: string;
        desc: string;
    };
    invalidCloudDiscoveryMetadata: {
        code: string;
        desc: string;
    };
    invalidAuthorityMetadata: {
        code: string;
        desc: string;
    };
    untrustedAuthority: {
        code: string;
        desc: string;
    };
    resourceRequestParametersRequired: {
        code: string;
        desc: string;
    };
};

// Warning: (ae-forgotten-export) The symbol "ClientCredentialRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type ClientCredentialRequest = Partial<Omit<ClientCredentialRequest_2, "scopes" | "resourceRequestMethod" | "resourceRequestUri">> & {
    scopes: Array<string>;
};

// @public (undocumented)
export class ConfidentialClientApplication extends ClientApplication implements IConfidentialClientApplication {
    constructor(configuration: Configuration);
    acquireTokenByClientCredential(request: ClientCredentialRequest): Promise<AuthenticationResult | null>;
    acquireTokenOnBehalfOf(request: OnBehalfOfRequest): Promise<AuthenticationResult | null>;
    }

// @public
export type Configuration = {
    auth: NodeAuthOptions;
    cache?: CacheOptions;
    system?: NodeSystemOptions;
};

// Warning: (ae-forgotten-export) The symbol "ICrypto" needs to be exported by the entry point index.d.ts
//
// @public
export class CryptoProvider implements ICrypto {
    constructor();
    base64Decode(input: string): string;
    base64Encode(input: string): string;
    createNewGuid(): string;
    // Warning: (ae-forgotten-export) The symbol "PkceCodes" needs to be exported by the entry point index.d.ts
    generatePkceCodes(): Promise<PkceCodes>;
    // (undocumented)
    getPublicKeyThumbprint(): Promise<string>;
    // (undocumented)
    signJwt(): Promise<string>;
}

// @public
export class Deserializer {
    // Warning: (ae-forgotten-export) The symbol "SerializedAccessTokenEntity" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "AccessTokenCache" needs to be exported by the entry point index.d.ts
    static deserializeAccessTokens(accessTokens: Record<string, SerializedAccessTokenEntity>): AccessTokenCache;
    // Warning: (ae-forgotten-export) The symbol "SerializedAccountEntity" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "AccountCache" needs to be exported by the entry point index.d.ts
    static deserializeAccounts(accounts: Record<string, SerializedAccountEntity>): AccountCache;
    // Warning: (ae-forgotten-export) The symbol "InMemoryCache" needs to be exported by the entry point index.d.ts
    static deserializeAllCache(jsonCache: JsonCache): InMemoryCache;
    // Warning: (ae-forgotten-export) The symbol "SerializedAppMetadataEntity" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "AppMetadataCache" needs to be exported by the entry point index.d.ts
    static deserializeAppMetadata(appMetadata: Record<string, SerializedAppMetadataEntity>): AppMetadataCache;
    // Warning: (ae-forgotten-export) The symbol "SerializedIdTokenEntity" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "IdTokenCache" needs to be exported by the entry point index.d.ts
    static deserializeIdTokens(idTokens: Record<string, SerializedIdTokenEntity>): IdTokenCache;
    // Warning: (ae-forgotten-export) The symbol "JsonCache" needs to be exported by the entry point index.d.ts
    static deserializeJSONBlob(jsonFile: string): JsonCache;
    // Warning: (ae-forgotten-export) The symbol "SerializedRefreshTokenEntity" needs to be exported by the entry point index.d.ts
    // Warning: (ae-forgotten-export) The symbol "RefreshTokenCache" needs to be exported by the entry point index.d.ts
    static deserializeRefreshTokens(refreshTokens: Record<string, SerializedRefreshTokenEntity>): RefreshTokenCache;
}

// Warning: (ae-forgotten-export) The symbol "DeviceCodeRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type DeviceCodeRequest = Partial<Omit<DeviceCodeRequest_2, "scopes" | "deviceCodeCallback" | "resourceRequestMethod" | "resourceRequestUri">> & {
    scopes: Array<string>;
    deviceCodeCallback: (response: DeviceCodeResponse) => void;
};

// @public (undocumented)
export interface ICachePlugin {
    // (undocumented)
    afterCacheAccess: (tokenCacheContext: TokenCacheContext) => Promise<void>;
    // (undocumented)
    beforeCacheAccess: (tokenCacheContext: TokenCacheContext) => Promise<void>;
}

// @public (undocumented)
export interface IConfidentialClientApplication {
    // (undocumented)
    acquireTokenByClientCredential(request: ClientCredentialRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenByCode(request: AuthorizationCodeRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenByRefreshToken(request: RefreshTokenRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenOnBehalfOf(request: OnBehalfOfRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenSilent(request: SilentFlowRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    getAuthCodeUrl(request: AuthorizationUrlRequest): Promise<string>;
    // (undocumented)
    getLogger(): Logger;
    // (undocumented)
    getTokenCache(): TokenCache;
    // (undocumented)
    setLogger(logger: Logger): void;
}

// @public
export interface INetworkModule {
    sendGetRequestAsync<T>(url: string, options?: NetworkRequestOptions): Promise<NetworkResponse<T>>;
    sendPostRequestAsync<T>(url: string, options?: NetworkRequestOptions): Promise<NetworkResponse<T>>;
}

// @public
export class InteractionRequiredAuthError extends ServerError {
    constructor(errorCode?: string, errorMessage?: string, subError?: string);
    // (undocumented)
    static isInteractionRequiredError(errorCode?: string, errorString?: string, subError?: string): boolean;
}

// @public (undocumented)
export interface IPublicClientApplication {
    // (undocumented)
    acquireTokenByCode(request: AuthorizationCodeRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenByDeviceCode(request: DeviceCodeRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenByRefreshToken(request: RefreshTokenRequest): Promise<AuthenticationResult | null>;
    // Warning: (ae-forgotten-export) The symbol "UsernamePasswordRequest" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    acquireTokenByUsernamePassword(request: UsernamePasswordRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    acquireTokenSilent(request: SilentFlowRequest): Promise<AuthenticationResult | null>;
    // (undocumented)
    getAuthCodeUrl(request: AuthorizationUrlRequest): Promise<string>;
    // (undocumented)
    getLogger(): Logger;
    // (undocumented)
    getTokenCache(): TokenCache;
    // (undocumented)
    setLogger(logger: Logger): void;
}

// @public (undocumented)
export interface ISerializableTokenCache {
    // (undocumented)
    deserialize: (cache: string) => void;
    // (undocumented)
    serialize: () => string;
}

// @public
export class Logger {
    // Warning: (ae-forgotten-export) The symbol "LoggerOptions" needs to be exported by the entry point index.d.ts
    constructor(loggerOptions: LoggerOptions, packageName?: string, packageVersion?: string);
    clone(packageName: string, packageVersion: string): Logger;
    error(message: string, correlationId?: string): void;
    errorPii(message: string, correlationId?: string): void;
    executeCallback(level: LogLevel, message: string, containsPii: boolean): void;
    info(message: string, correlationId?: string): void;
    infoPii(message: string, correlationId?: string): void;
    isPiiLoggingEnabled(): boolean;
    verbose(message: string, correlationId?: string): void;
    verbosePii(message: string, correlationId?: string): void;
    warning(message: string, correlationId?: string): void;
    warningPii(message: string, correlationId?: string): void;
}

// @public
export enum LogLevel {
    // (undocumented)
    Error = 0,
    // (undocumented)
    Info = 2,
    // (undocumented)
    Verbose = 3,
    // (undocumented)
    Warning = 1
}

// @public
export type NetworkRequestOptions = {
    headers?: Record<string, string>;
    body?: string;
};

// @public (undocumented)
export type NetworkResponse<T> = {
    headers: Record<string, string>;
    body: T;
    status: number;
};

// Warning: (ae-forgotten-export) The symbol "OnBehalfOfRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type OnBehalfOfRequest = Partial<Omit<OnBehalfOfRequest_2, "oboAssertion" | "scopes" | "resourceRequestMethod" | "resourceRequestUri">> & {
    oboAssertion: string;
    scopes: Array<string>;
};

// @public
export const PromptValue: {
    LOGIN: string;
    SELECT_ACCOUNT: string;
    CONSENT: string;
    NONE: string;
};

// @public
export enum ProtocolMode {
    // (undocumented)
    AAD = "AAD",
    // (undocumented)
    OIDC = "OIDC"
}

// @public
export class PublicClientApplication extends ClientApplication implements IPublicClientApplication {
    constructor(configuration: Configuration);
    acquireTokenByDeviceCode(request: DeviceCodeRequest): Promise<AuthenticationResult | null>;
    acquireTokenByUsernamePassword(request: UsernamePasswordRequest): Promise<AuthenticationResult | null>;
}

// Warning: (ae-forgotten-export) The symbol "RefreshTokenRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type RefreshTokenRequest = Partial<Omit<RefreshTokenRequest_2, "scopes" | "refreshToken" | "authenticationScheme" | "resourceRequestMethod" | "resourceRequestUri">> & {
    scopes: Array<string>;
    refreshToken: string;
};

// @public
export enum ResponseMode {
    // (undocumented)
    FORM_POST = "form_post",
    // (undocumented)
    FRAGMENT = "fragment",
    // (undocumented)
    QUERY = "query"
}

// @public (undocumented)
export class Serializer {
    static serializeAccessTokens(atCache: AccessTokenCache): Record<string, SerializedAccessTokenEntity>;
    static serializeAccounts(accCache: AccountCache): Record<string, SerializedAccountEntity>;
    static serializeAllCache(inMemCache: InMemoryCache): JsonCache;
    static serializeAppMetadata(amdtCache: AppMetadataCache): Record<string, SerializedAppMetadataEntity>;
    static serializeIdTokens(idTCache: IdTokenCache): Record<string, SerializedIdTokenEntity>;
    static serializeJSONBlob(data: JsonCache): string;
    static serializeRefreshTokens(rtCache: RefreshTokenCache): Record<string, SerializedRefreshTokenEntity>;
}

// @public
export class ServerError extends AuthError {
    constructor(errorCode?: string, errorMessage?: string, subError?: string);
}

// Warning: (ae-forgotten-export) The symbol "SilentFlowRequest" needs to be exported by the entry point index.d.ts
//
// @public
export type SilentFlowRequest = Partial<Omit<SilentFlowRequest_2, "account" | "scopes" | "resourceRequestMethod" | "resourceRequestUri">> & {
    account: AccountInfo;
    scopes: Array<string>;
};

// Warning: (ae-forgotten-export) The symbol "CacheManager" needs to be exported by the entry point index.d.ts
//
// @public
class Storage_2 extends CacheManager {
    constructor(logger: Logger, clientId: string, cryptoImpl: ICrypto);
    cacheToInMemoryCache(cache: CacheKVStore): InMemoryCache;
    clear(): void;
    containsKey(key: string): boolean;
    // (undocumented)
    emitChange(): void;
    static generateInMemoryCache(cache: string): InMemoryCache;
    static generateJsonCache(inMemoryCache: InMemoryCache): JsonCache;
    // Warning: (ae-forgotten-export) The symbol "AccessTokenEntity" needs to be exported by the entry point index.d.ts
    getAccessTokenCredential(accessTokenKey: string): AccessTokenEntity | null;
    // Warning: (ae-forgotten-export) The symbol "AccountEntity" needs to be exported by the entry point index.d.ts
    getAccount(accountKey: string): AccountEntity | null;
    // Warning: (ae-forgotten-export) The symbol "AppMetadataEntity" needs to be exported by the entry point index.d.ts
    getAppMetadata(appMetadataKey: string): AppMetadataEntity | null;
    // Warning: (ae-forgotten-export) The symbol "AuthorityMetadataEntity" needs to be exported by the entry point index.d.ts
    getAuthorityMetadata(key: string): AuthorityMetadataEntity | null;
    getAuthorityMetadataKeys(): Array<string>;
    getCache(): CacheKVStore;
    // Warning: (ae-forgotten-export) The symbol "IdTokenEntity" needs to be exported by the entry point index.d.ts
    getIdTokenCredential(idTokenKey: string): IdTokenEntity | null;
    getInMemoryCache(): InMemoryCache;
    getItem(key: string): ValidCacheType;
    getKeys(): string[];
    // Warning: (ae-forgotten-export) The symbol "RefreshTokenEntity" needs to be exported by the entry point index.d.ts
    getRefreshTokenCredential(refreshTokenKey: string): RefreshTokenEntity | null;
    // Warning: (ae-forgotten-export) The symbol "ServerTelemetryEntity" needs to be exported by the entry point index.d.ts
    getServerTelemetry(serverTelemetrykey: string): ServerTelemetryEntity | null;
    // Warning: (ae-forgotten-export) The symbol "ThrottlingEntity" needs to be exported by the entry point index.d.ts
    getThrottlingCache(throttlingCacheKey: string): ThrottlingEntity | null;
    inMemoryCacheToCache(inMemoryCache: InMemoryCache): CacheKVStore;
    // (undocumented)
    registerChangeEmitter(func: () => void): void;
    removeItem(key: string): boolean;
    setAccessTokenCredential(accessToken: AccessTokenEntity): void;
    setAccount(account: AccountEntity): void;
    setAppMetadata(appMetadata: AppMetadataEntity): void;
    setAuthorityMetadata(key: string, metadata: AuthorityMetadataEntity): void;
    setCache(cache: CacheKVStore): void;
    setIdTokenCredential(idToken: IdTokenEntity): void;
    setInMemoryCache(inMemoryCache: InMemoryCache): void;
    setItem(key: string, value: ValidCacheType): void;
    setRefreshTokenCredential(refreshToken: RefreshTokenEntity): void;
    setServerTelemetry(serverTelemetryKey: string, serverTelemetry: ServerTelemetryEntity): void;
    setThrottlingCache(throttlingCacheKey: string, throttlingCache: ThrottlingEntity): void;
}

export { Storage_2 as Storage }

// Warning: (ae-forgotten-export) The symbol "ITokenCache" needs to be exported by the entry point index.d.ts
//
// @public
export class TokenCache implements ISerializableTokenCache, ITokenCache {
    constructor(storage: Storage_2, logger: Logger, cachePlugin?: ICachePlugin);
    deserialize(cache: string): void;
    getAccountByHomeId(homeAccountId: string): Promise<AccountInfo | null>;
    getAccountByLocalId(localAccountId: string): Promise<AccountInfo | null>;
    getAllAccounts(): Promise<AccountInfo[]>;
    // (undocumented)
    getKVStore(): CacheKVStore;
    hasChanged(): boolean;
    removeAccount(account: AccountInfo): Promise<void>;
    serialize(): string;
    }

// @public (undocumented)
export class TokenCacheContext {
    constructor(tokenCache: ISerializableTokenCache, hasChanged: boolean);
    // (undocumented)
    cache: ISerializableTokenCache;
    // (undocumented)
    get cacheHasChanged(): boolean;
    // (undocumented)
    hasChanged: boolean;
    // (undocumented)
    get tokenCache(): ISerializableTokenCache;
}


// Warnings were encountered during analysis:
//
// dist/config/Configuration.d.ts:53:5 - (ae-forgotten-export) The symbol "NodeAuthOptions" needs to be exported by the entry point index.d.ts
// dist/config/Configuration.d.ts:54:5 - (ae-forgotten-export) The symbol "CacheOptions" needs to be exported by the entry point index.d.ts
// dist/config/Configuration.d.ts:55:5 - (ae-forgotten-export) The symbol "NodeSystemOptions" needs to be exported by the entry point index.d.ts
// dist/request/DeviceCodeRequest.d.ts:12:5 - (ae-forgotten-export) The symbol "DeviceCodeResponse" needs to be exported by the entry point index.d.ts

// (No @packageDocumentation comment for this package)

```