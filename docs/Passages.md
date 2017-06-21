# Web Api Openfield - Passages

# Principe generaux

test ines
#tes par
##par 2

ifsdfsdfdsgdg
sjqsdhksdhksq

fqfqsfsq


		/// <summary>
        /// Get details for a specific event using its unique identifier in the Openfield's repository
        /// </summary>
        /// <remarks>Find an Transaction using its Openfield id (PublicId)</remarks>
        /// <param name="id">Openfield Id (guid format)</param>
        /// <returns>One Order or error code</returns>
        [SwaggerOperation("GetPassage")]
        [SwaggerResponse(HttpStatusCode.OK)]
        [SwaggerResponse(HttpStatusCode.NotFound)]
        [SwaggerResponse(HttpStatusCode.Unauthorized)]
        [SwaggerResponse(HttpStatusCode.BadRequest)]
        [ResponseType(typeof(dtoObject))]
        [MonitoringFilter]
        [OpenfieldIdentityValidator]
        public override async Task<HttpResponseMessage> Get(string id)
        {
            return await base.Get(id);
        }

        /// <summary>
        ///  Get event(s) by search key
        /// </summary>
        /// <remarks>"Find transactions by transaction id, date, location and much more.
        /// The search keys available are : 
        /// 1. ExternalId : returns an transaction using its number in the partner's repository.
        /// 2. --COMING SOON -- ControllerId : returns transactions passed by the specified controller.
        /// 3. --COMING SOON -- ControllerName : returns transactions passed by the specified controller.
        /// 4. MediaId : returns transactions passed for its mediaID
        /// 5. VenueExternalId : finds transactions the partner id of the venue
        /// 6. VenueName : finds transactions using the partner name of the venue
        /// 7. EventExternalId : finds transactions in a specific location using the partner id of the Event
        /// 8. PartyId : finds transactions  using the partner id of the party (openfield Id)
        /// 9. --COMING SOON -- SpaceId : finds transactions using the partner ID of the space (openfield id)
        /// </remarks>
        /// <param name="key">Search Key. ex:MediaId</param>
        /// <param name="value">Search value</param>
        /// <returns>List of passages</returns>
        [SwaggerOperation("GetPassage")]
        [SwaggerResponse(HttpStatusCode.OK, "Item found")]
        [SwaggerResponse(HttpStatusCode.NotFound, "Item not found")]
        [SwaggerResponse(HttpStatusCode.Unauthorized)]
        [SwaggerResponse(HttpStatusCode.BadRequest)]
        [MonitoringFilter]
        [OpenfieldIdentityValidator]
        [ResponseType(typeof(IEnumerable<pivot>))]
        [Route("api/passage/tag/{key}/{value}")]
        public override async Task<HttpResponseMessage> Get([FromUri]string key, [FromUri]string value)
        {
            return await base.Get(key, value);
        }

        /// <summary>
        /// Create transaction. If it already exists, it will be updated.
        /// </summary>
        /// <param name="item">transaction to create</param>
        /// <returns>Request status. If ok, response contains Openfield ID and order version</returns>
        [SwaggerOperation("CreatePassage")]
        [SwaggerResponse(HttpStatusCode.Created)]
        [SwaggerResponse(HttpStatusCode.NotFound)]
        [SwaggerResponse(HttpStatusCode.Unauthorized)]
        [SwaggerResponse(HttpStatusCode.BadRequest)]
        [OpenfieldIdentityValidator]
        //[ClaimsAuthorize()]
        [MonitoringFilter]
        [WebApiValidation]
        public override async Task<HttpResponseMessage> Post([FromBody]dtoObject item)
        {
            return await base.Post(item);
        }

        /// <summary>
        /// Update transaction.
        /// </summary>
        /// <param name="item">transaction to update</param>
        /// <returns>Request status. If ok, response contains Openfield ID and order version</returns>



















## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
