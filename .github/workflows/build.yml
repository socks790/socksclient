
package com.socks.client;

import net.fabricmc.api.ClientModInitializer;
import net.fabricmc.fabric.api.client.rendering.v1.hud.HudElementRegistry;
import net.fabricmc.fabric.api.client.rendering.v1.hud.VanillaHudElements;
import net.fabricmc.fabric.api.client.screen.v1.ScreenEvents;
import net.minecraft.client.Minecraft;
import net.minecraft.client.gui.GuiGraphicsExtractor;
import net.minecraft.client.renderer.RenderPipelines;
import net.minecraft.resources.Identifier;

public class SocksClientMod implements ClientModInitializer {

    private static final Identifier WATERMARK =
            Identifier.fromNamespaceAndPath("socksclient", "textures/gui/watermark.png");

    private static final int TEX_W = 177;
    private static final int TEX_H = 40;
    private static final int MARGIN = 6;

    @Override
    public void onInitializeClient() {

        HudElementRegistry.attachElementBefore(
                VanillaHudElements.CHAT,
                Identifier.fromNamespaceAndPath("socksclient", "watermark"),
                (graphics, tracker) -> {
                    Minecraft mc = Minecraft.getInstance();

                    if (mc.gui.screen() == null) {
                        draw(
                                graphics,
                                mc.getWindow().getGuiScaledWidth(),
                                mc.getWindow().getGuiScaledHeight()
                        );
                    }
                }
        );

        ScreenEvents.AFTER_INIT.register((client, screen, w, h) ->
                ScreenEvents.afterExtract(screen).register(
                        (s, graphics, mouseX, mouseY, tickProgress) ->
                                draw(graphics, s.width, s.height)
                )
        );
    }

    private static void draw(GuiGraphicsExtractor g, int sw, int sh) {

        int x = sw - TEX_W - MARGIN;
        int y = sh - TEX_H - MARGIN;

        g.blit(
                RenderPipelines.GUI_TEXTURED,
                WATERMARK,
                x, y,
                0, 0,
                TEX_W, TEX_H,
                TEX_W, TEX_H,
                TEX_W, TEX_H
        );
    }
}
